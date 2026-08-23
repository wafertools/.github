# Security policy

Applies to every repository in the [wafertools](https://github.com/wafertools) organisation.

## Supported versions

Both projects are pre-1.0 and ship fixes forward only: the **latest published version** is
the supported one. There are no backported patch branches.

| Project | Supported |
| --- | --- |
| [`@wafertools/wafermap`](https://www.npmjs.com/package/@wafertools/wafermap) | Latest `0.x` release |
| [`@wafertools/testdata-parser`](https://www.npmjs.com/package/@wafertools/testdata-parser) | Latest `0.x` release |
| [tsmap](https://github.com/wafertools/tsmap/releases) | Latest release |

## Reporting a vulnerability

Please report privately, not as a public issue: open a draft advisory through
**Security → Report a vulnerability** on the affected repository
([wafermap](https://github.com/wafertools/wafermap/security/advisories/new) ·
[tsmap](https://github.com/wafertools/tsmap/security/advisories/new)).

This is a one-maintainer project, so please allow a few days for a first response. You will
get an acknowledgement, an assessment, and — if the report is valid — credit in the release
notes for the fix, unless you would rather not be named.

## What is worth reporting

The parts of these projects where a security bug is plausible:

- **Parsing untrusted files.** STDF, ATDF, CSV, JSON and Parquet files are parsed locally,
  in Rust (natively and as WebAssembly). Memory safety is largely handled by the language,
  but a crafted file that causes a panic, an unbounded allocation, or a hang is a real bug —
  wafer files routinely arrive from other people's testers.
- **`--url` / `?dataUrl=` / `tsmap://` ingestion.** tsmap can be handed a URL by a caller
  application or a web link. Anything that lets a link reach further than fetching and
  parsing the data it names — writing outside the temp file it materialises, or executing
  anything — is in scope.
- **`--url-headers`.** This file is the one place in tsmap where a credential sits. Anything
  that leaks its contents (into logs, error messages, a subsequent request to a different
  host) is in scope.
- **File association registration**, which writes to the Windows registry under
  `HKEY_CURRENT_USER\Software\Classes` and to Linux `mimeapps.list` / shared-mime-info.
- **Rendered content in wafermap.** Bin names, test names, and lot metadata come from the
  data file and are displayed in the DOM; anything that makes such a string execute rather
  than display is in scope.

## What is not a vulnerability

- **Unsigned installers.** tsmap's installers are deliberately not code-signed, and the OS
  warnings that follow are expected — see the
  [README](https://github.com/wafertools/tsmap#installing-past-security-warnings).
- **A URL passed to tsmap needing no authentication of its own.** `--url` sends no
  credentials unless you supply `--url-headers`; the URL is expected to be self-authenticating
  (a presigned link). This is by design, and documented.
- **Data leaving your machine.** It does not. Both the desktop and browser builds parse
  locally with no upload step; a report showing otherwise, however, is very much a
  vulnerability.
