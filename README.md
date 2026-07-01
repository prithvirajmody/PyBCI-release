# PyBCI — Releases

Official public download home for **PyBCI**, the interactive development
workspace for brain–computer interfaces by
[Efferent Systems](https://efferent.systems).

This repository hosts the **packaged desktop application** only. The PyBCI source
code lives in a separate private repository; the builds here bundle the PyBCI
runtime and do **not** require Python.

> ## ⚠️ Early access
>
> PyBCI is currently in **early access**. Builds are **not yet code-signed**, so
> Windows and macOS may show an "unknown publisher", "unidentified developer", or
> SmartScreen-style warning. **Only continue if you received the download link
> directly from the PyBCI team.** Apple/Windows/GPG signing certificates are being
> provisioned; the fully signed 1.0.0 production release will follow.

## Download

Go to the [latest early-access release](https://github.com/prithvirajmody/PyBCI-release/releases)
and download the file for your operating system:

| Platform | Artifact |
|----------|----------|
| Windows  | `PyBCI-<version>-windows-x64.zip` |
| macOS    | `PyBCI-<version>-macos-x64.dmg` (or `.zip`) |
| Linux    | `PyBCI-<version>-linux-x64.tar.gz` |

## Install

See [INSTALL.md](INSTALL.md) for per-OS install and first-launch steps.

## Optional verification

Each release includes `SHA-256SUMS`. Most early-access users do not need to
verify manually. Technical users can confirm a download matches the published
checksum — see [VERIFY.md](VERIFY.md).

## Support

Questions or problems: [hello@efferent.systems](mailto:hello@efferent.systems?subject=PyBCI%20help).
When reporting an issue, include the PyBCI version, your operating system, the
step that failed, and the exact error text. Do not include API keys, secrets, or
private recording data.
