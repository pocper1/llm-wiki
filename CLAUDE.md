# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this repo is

This is `pocper1`'s personal digital-garden wiki, built on **Quartz v5** (a static site generator, `@jackyzha0/quartz`). It contains both the Quartz engine (`quartz/`) and the site's own content/config (`content/`, `quartz.config.yaml`). The site's notes live in `content/` (currently minimal — likely synced from Obsidian over time) and are built into static HTML in `public/`, then deployed as a Cloudflare Workers static-asset site (`wrangler.jsonc`, project name `llm-wiki`, base URL `wiki.jimmystack.dev`). A `Dockerfile` also exists for a container-based build/serve path.

Note: `.github/workflows/*.yaml` (CI, deploy-preview, deploy-v5, docker-build-push) are inherited from the upstream `jackyzha0/quartz` repo and gate on `github.repository == 'jackyzha0/quartz'`, so they are effectively inert in this fork/repo.

## Commands

```shell
npm install                          # install deps (also runs prebuild -> install-plugins)
npx quartz build --serve             # build + serve locally with hot reload (default port 8080)
npx quartz build -d docs             # build into an alternate output dir (e.g. what CI uses)
npm run check                        # tsc --noEmit + prettier --check (run before considering work done)
npm run format                       # prettier --write
npm test                             # runs all *.test.js/*.test.ts via `tsx --test`
npx tsx --test quartz/util/path.test.ts      # run a single test file
npx quartz plugin install --from-config      # install plugins referenced in quartz.config.yaml but missing from lockfile
npx quartz plugin install --clean            # restore plugins to the commits pinned in quartz.lock.json (used in CI)
npx quartz plugin add github:quartz-community/<name>   # add a new community plugin
npx quartz plugin remove <name>       # remove a plugin
npx quartz plugin prune               # remove plugins installed but no longer referenced in config
npx quartz tui                        # interactive plugin/layout manager
```

Tests are plain Node `node:test` files (`*.test.ts` / `*.test.js`) run through `tsx`; there's no separate test runner config. `npm run check` is the fast correctness gate (types + formatting) — run it after any non-trivial change.

## High-level architecture

### Build pipeline (`npx quartz build`)

1. `package.json` `bin.quartz` points to `quartz/bootstrap-cli.mjs`. It parses CLI args (yargs), transpiles/bundles the rest of Quartz with esbuild (handling `.scss` imports and separately bundling any `*.inline.ts` client-side script for the browser), then dynamically imports the built `quartz/build.ts` from a cache file and invokes it. If `--serve` is set it also starts a WebSocket hot-reload server and an HTTP file server, plus a source file watcher that triggers esbuild rebuilds.
2. `quartz/build.ts` cleans the output dir, globs `content/` (respecting `.gitignore`), and parses Markdown via a `unified`/`remark`/`rehype` pipeline: text-transform -> mdast (remark-parse) -> markdown-to-markdown plugins -> mdast-to-hast (remark-rehype) -> html-to-html plugins. Large content sets (>128 files) are parsed across worker threads via `workerpool` (see `quartz/worker.ts`).
3. Filter plugins decide which parsed content actually gets published.
4. Emitter plugins reduce over the filtered content to produce output files. HTML-emitting plugins convert hast -> JSX (`hast-util-to-jsx-runtime`, Preact) and statically render with `preact-render-to-string`; the core rendering logic is in `quartz/components/renderPage.tsx`. CSS is minified/prefixed with Lightning CSS; scripts are split into `beforeDOMLoaded`/`afterDOMLoaded`.
5. In `--serve` mode, a second watcher tracks only content-file changes, incrementally updates content in memory, and reruns filters/emitters (debounced 250ms), then signals the browser to reload.
6. On the client: page loads `public/index.css` and `public/prescript.js` (critical), then `public/postscript.js` (non-critical). A synthetic `"nav"` event fires after load (and on every client-side navigation if `enableSPA` is set) so components can wire up DOM behavior; a `"render"` event fires on in-place DOM updates (e.g. after content decryption) without a full navigation.

Full walkthrough: `docs/advanced/architecture.md`. Path/slug type system (`FilePath`, `FullSlug`, `SimpleSlug`, `RelativeURL` — nominal-typed via brands, converted through `quartz/util/path.ts`): `docs/advanced/paths.md`.

### Plugin system

Quartz v5's plugins are **standalone Git repositories**, not local code. `npx quartz plugin add github:quartz-community/<name>` clones a plugin into `.quartz/plugins/<name>/`, and `.quartz/plugins/index.ts` (auto-generated, gitignored) re-exports everything installed. `quartz.lock.json` pins each plugin's commit hash for reproducible installs (`plugin install --clean` restores from this lockfile — this is what CI/Docker use). Plugins ship pre-built `dist/` so install is normally just a git clone, no build step.

Shared code across plugins is layered into community packages with a strict dependency direction:

```
@quartz-community/types    (no deps — contracts/interfaces, vfile DataMap augmentation)
  ↑
@quartz-community/utils    (path/DOM/sort/date/jsx helpers; depends on types)
  ↑
@quartz-community/runtime  (browser-only: nav/event/storage helpers; depends on types+utils)
  ↑
plugins                    (depend on any combination of the above)
```

Plugins must import from these packages, **not** from `@jackyzha0/quartz` or `vfile` directly (see the import table in `docs/advanced/making plugins.md`).

There are five plugin capabilities (not mutually exclusive — one plugin repo can be several):

- **Transformer** (`quartz/plugins/transformers/`) — maps over a single file's content (`textTransform`, `markdownPlugins` (remark), `htmlPlugins` (rehype), `externalResources`).
- **Filter** (`quartz/plugins/filters/`) — `shouldPublish(ctx, content)` decides what gets emitted.
- **Emitter** (`quartz/plugins/emitters/`) — reduces over all filtered content to produce output files (`emit`, optional `partialEmit` for incremental dev-server rebuilds, `getQuartzComponents`).
- **Page Type** (`quartz/plugins/pageTypes/`) — defines how a category of pages renders (`match`, optional `generate` for virtual pages like folder/tag indices, `layout`, `frame`, `body`). `quartz/plugins/pageTypes/dispatcher.ts` is the `PageTypeDispatcher` emitter that routes each slug to the right page type.
- **Bases View** — custom database-like view renderers registered into a global `ViewRegistry` singleton by the `bases-page` plugin.

Local, in-repo plugin wiring: `quartz/plugins/index.ts` re-exports all categories and assembles `StaticResources` (css/js/additionalHead) by concatenating what every transformer/emitter contributes, plus the dev-mode hot-reload websocket script.

Full authoring guide (including i18n conventions for plugin-facing strings, and how to ship a plugin-provided page frame): `docs/advanced/making plugins.md`.

### Page frames

Frames control the _inner_ HTML structure of a page (the outer shell — `<html>`, `<head>`, `<body>`, `#quartz-root` — is fixed for SPA routing to work). Lives in `quartz/components/frames/`: `types.ts` (interfaces), built-ins `DefaultFrame.tsx` (3-column), `FullWidthFrame.tsx`, `MinimalFrame.tsx`, `registry.ts` (`FrameRegistry` singleton for plugin-registered frames), `index.ts` (`resolveFrame()`). Resolution order: YAML `layout.byPageType.<name>.template` override -> plugin-registered frame by name -> built-in frame by name -> `"default"`. The active frame is set as `data-frame` on `.page` for frame-scoped CSS (`quartz/styles/base.scss`).

### Configuration

- `quartz.config.yaml` — this site's actual config (general `configuration:` block + ordered `plugins:` list with `enabled`/`options`/`order`/`layout` per entry, plus a top-level `layout:` for groups and per-page-type slot overrides). Edit this for day-to-day site changes.
- `quartz.config.default.yaml` — fallback config used when no `quartz.config.yaml` is present (used by `plugin resolve`/`plugin prune` and CI-style environments as the source of truth).
- `quartz.ts` — the actual JS/TS entrypoint (`loadQuartzConfig()` / `loadQuartzLayout()` from `quartz/plugins/loader/config-loader.ts`). Plugin options that need real JS callbacks (not expressible in YAML) are set here via `ExternalPlugin.<Plugin>({...})` calls from `./.quartz/plugins`, placed _before_ `loadQuartzConfig()` — these merge with and override the YAML options at instantiation time.

Full option reference (analytics providers, theming, `ignorePatterns`/private pages, i18n locale, etc.): `docs/configuration.md`.
