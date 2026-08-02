<picture>
  <source media="(prefers-color-scheme: dark)" srcset="profile/icon-dark.png">
  <img src="profile/icon-light.png" width="72" alt="wafertools">
</picture>

# wafertools

Tools for reviewing semiconductor wafer test data: rendering wafer maps, computing yield
and spatial statistics, and browsing STDF/ATDF/CSV/JSON test results.

## Projects

**[wafermap](https://github.com/wafertools/wafermap)** — `@wafertools/wafermap` on npm

Interactive wafer map visualization and yield analysis for semiconductor test data. Hard
bins, soft bins, test values, retests, edge exclusion, reticle overlays, spatial
statistics, failure clustering, and lot-level trend analysis — pure ES modules, no runtime
dependencies, no server required.
[Docs](https://wafertools.github.io/wafermap/) · [npm](https://www.npmjs.com/package/@wafertools/wafermap)

**[tsmap](https://github.com/wafertools/tsmap)**

Desktop wafer map viewer built on `wafermap` — Tauri v2, with a Rust/WASM parser for STDF
and a TypeScript loader for ATDF/CSV/JSON. Ships as native installers for Linux, macOS, and
Windows, and as a no-install browser app.
[Browser app](https://wafertools.github.io/tsmap/app/) · [Releases](https://github.com/wafertools/tsmap/releases)

## Community

Questions, ideas, or want to show off a wafer map you built? Use [GitHub
Discussions](https://github.com/wafertools/.github/discussions) — open to anyone using
either project.
