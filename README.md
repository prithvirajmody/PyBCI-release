# PyBCI — Releases

Official public download home for **PyBCI**, the interactive development
workspace for brain–computer interfaces by
[Efferent Systems](https://efferent.systems).

This repository hosts the **signed, packaged desktop application** only. The
PyBCI source code lives in a separate private repository; the builds here bundle
the PyBCI runtime and do **not** require Python.

## Download

- **Latest release:** [github.com/prithvirajmody/PyBCI-release/releases/latest](https://github.com/prithvirajmody/PyBCI-release/releases/latest)
- Or use the download page on the website: [efferent.systems/download](https://efferent.systems/download)

Each release provides x64 builds for Windows, macOS, and Linux, plus
`SHA-256SUMS` and platform signatures.

| Platform | Artifact |
|----------|----------|
| Windows  | `PyBCI-<version>-windows-x64.zip` |
| macOS    | `PyBCI-<version>-macos-x64.dmg` (or `.zip`) |
| Linux    | `PyBCI-<version>-linux-x64.tar.gz` (+ `.asc`) |

## Install

See [INSTALL.md](INSTALL.md) for per-OS install and first-launch steps.

## Verify before you run

Download only from this repository's Releases page or the official website.
Always verify the SHA-256 checksum and the platform signature before opening an
artifact — see [VERIFY.md](VERIFY.md).

## Support

Questions or problems: [hello@efferent.systems](mailto:hello@efferent.systems?subject=PyBCI%20help).
When reporting an issue, include the PyBCI version, your operating system, the
step that failed, and the exact error text. Do not include API keys, secrets, or
private recording data.
