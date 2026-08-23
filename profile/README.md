<picture>
  <source media="(prefers-color-scheme: dark)" srcset="icon-dark.png">
  <img src="icon-light.png" width="72" alt="wafertools">
</picture>

# wafertools

Tools for reviewing semiconductor wafer test data: rendering wafer maps, computing yield
and spatial statistics, and browsing STDF/ATDF/CSV/JSON/Parquet test results.

**📣 [What's New](https://wafertools.github.io/whats-new/)** — a curated, plain-language
timeline of new capabilities across both projects.

## Projects

**[wafermap](https://github.com/wafertools/wafermap)** — `@wafertools/wafermap` on npm

Interactive wafer map visualization and yield analysis for semiconductor test data. Hard
bins, soft bins, test values, retests, edge exclusion, reticle overlays, spatial
statistics, failure clustering, and lot-level trend analysis — pure ES modules, no runtime
dependencies, no server required.
[Docs](https://wafertools.github.io/wafermap/) · [npm](https://www.npmjs.com/package/@wafertools/wafermap)

**[tsmap](https://github.com/wafertools/tsmap)**

Desktop and browser wafer map viewer built on `wafermap` — Tauri v2, with Rust parsers for
STDF, ATDF, CSV, JSON, and Parquet, compiled to WebAssembly for the browser build. Ships as
native installers for Linux, macOS, and Windows, and as a no-install browser app.
[Browser app](https://wafertools.github.io/tsmap/app/) · [Releases](https://github.com/wafertools/tsmap/releases)

## Community

Questions, ideas, or want to show off a wafer map you built? Use [GitHub
Discussions](https://github.com/wafertools/.github/discussions) — open to anyone using
either project.
