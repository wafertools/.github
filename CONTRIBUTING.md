# Contributing to wafertools

This file covers every repository in the [wafertools](https://github.com/wafertools)
organisation: [wafermap](https://github.com/wafertools/wafermap),
[tsmap](https://github.com/wafertools/tsmap), and the
[docs site](https://github.com/wafertools/wafertools.github.io).

## Before you open anything

**Questions, ideas, and "is this the right way to do X?"** belong in
[Discussions](https://github.com/wafertools/.github/discussions) — one space shared by both
projects, since most questions turn out to span them.

**Bugs** belong in the issue tracker of the repository where the bug appears. If you are not
sure whether a rendering problem is tsmap's or wafermap's, file it against tsmap and it will
be moved if it turns out to originate in the library.

## Reporting a bug

The two things that make a report actionable here are the **data shape** and the **platform**:

- Format (STDF/ATDF/CSV/JSON/Parquet), roughly how many wafers, dies, and tests, and whether
  die X/Y positions are present.
- Desktop or browser build, and which OS — several past bugs existed on exactly one of
  Linux/WebKitGTK, Windows/WebView2, or macOS/WKWebView.
- The version: tsmap prints `tsmap v<version> (<build date>)` as the first line of its log
  panel at startup; wafermap's is the version in your `package.json`.

Please do not attach real production test data. A synthetic file that reproduces the problem
is far more useful — tsmap's `scripts/generate_*.py` can produce one in most shapes.

## Changes

Both projects are actively developed by one maintainer, so **open an issue or a discussion
before writing a large patch.** A change that duplicates work already in progress, or that
cuts across the wafermap/tsmap boundary, is likely to need reshaping regardless of quality.
Small, self-contained fixes are welcome directly as a pull request.

If you are changing something in both projects, note that wafermap is developed against tsmap
as its main integration test, and the two are released independently — a tsmap release can
never depend on an unpublished wafermap.

### Working in wafermap

```bash
npm install
npm run check      # types, examples manifest, agents/toolbar doc guards
npm test
npm run dev        # docs site with live examples at localhost:8001
```

New UI work must follow
[UI_STANDARDS.md](https://github.com/wafertools/wafermap/blob/main/UI_STANDARDS.md) — WCAG 2.1
AA and the WAI-ARIA authoring practices, with a checklist for new menus, comboboxes and
popups. It is the shared baseline for both projects.

### Working in tsmap

```bash
npm install
npm run tauri dev  # full desktop app
npm run dev:web    # browser build at localhost:5301
npx tsc --noEmit
cargo check        # from src-tauri/
cargo test         # from packages/parsers/
```

A gap you hit in wafermap while working on tsmap belongs in a
[wafermap issue](https://github.com/wafertools/wafermap/issues) — what the problem is, where
in wafermap it originates, and a suggested fix. A tsmap-side workaround is temporary; the
issue is the permanent record.

## Licence

Both projects are MIT. By contributing you agree your contribution is licensed the same way.
