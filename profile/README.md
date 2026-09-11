<picture>
  <source media="(prefers-color-scheme: dark)" srcset="icon-dark.png">
  <img src="icon-light.png" width="72" alt="wafertools">
</picture>

# wafertools

Tools for reviewing semiconductor wafer test data: rendering wafer maps, computing yield
and spatial statistics, and browsing STDF/ATDF/CSV/JSON/Parquet test results.

**📣 [What's New](https://wafertools.github.io/whats-new/)** — a curated, plain-language
timeline of new capabilities across both projects.

## Which one do you want?

**Want to look at wafer data? → [tsmap](https://github.com/wafertools/tsmap)**

A finished, free, MIT-licensed application. Open STDF, ATDF, CSV, JSON or Parquet (plus
`.gz`/`.zip`) and get interactive yield maps, parametric heat maps, findings, a chart
suite, lot galleries and exportable reports — no code, no account, no upload. Native
installers for Linux, macOS and Windows, and a no-install browser build where files are
still parsed entirely on your own machine. **Most people want this one.**
[Open in the browser](https://wafertools.github.io/tsmap/app/) · [Releases](https://github.com/wafertools/tsmap/releases) · [Docs](https://wafertools.github.io/tsmap/)

**Building an application? → [wafermap](https://github.com/wafertools/wafermap)** — `@wafertools/wafermap` on npm

The rendering and analysis library tsmap is built on. Interactive wafer map visualization
and yield analysis: hard bins, soft bins, test values, retests, edge exclusion, reticle
overlays, spatial statistics, failure clustering and lot-level trend analysis — pure ES
modules, no runtime dependencies, no server required. Two calls render a working map.

Reach for it when you need wafer maps *inside* your own application, a data source tsmap
doesn't read, or behaviour it doesn't offer — you can always start with tsmap and
integrate later.
[Docs](https://wafertools.github.io/wafermap/) · [Quick Start](https://wafertools.github.io/wafermap/quickstart/) · [npm](https://www.npmjs.com/package/@wafertools/wafermap)

## Why these exist

Both are written by **Paul Robins**, after nearly four decades in semiconductor test —
most of it building test data analysis tools: wafer map and chart viewers, and the
platforms they were built on. That work leaned on free software throughout, and these
projects are some of it going back the other way. Both are MIT licensed.
[More →](https://wafertools.github.io/)

## Community

Questions, ideas, or want to show off a wafer map you built? Use [GitHub
Discussions](https://github.com/wafertools/.github/discussions) — open to anyone using
either project.
