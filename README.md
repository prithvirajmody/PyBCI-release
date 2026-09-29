# PyBCI

**Desktop workspace for EEG acquisition, preprocessing, visualization, and model training.**

Official public download home for **PyBCI**, the interactive development
workspace for brain–computer interfaces by
[Efferent Systems](https://efferentsystems.com).

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

## What PyBCI is for

PyBCI brings brain–computer interface workflows into one desktop application: connect or import signals, configure processing steps, inspect results, and train models. The application is built by Efferent Systems; this repository provides public downloads, installation guidance, and support.

**Distribution:** public early-access binaries; source code is maintained privately. The latest published build in this repository is `v1.0.0-ea.2`. Early access is distinct from a signed stable release.

## Download

Go to the [latest early-access release](https://github.com/prithvirajmody/PyBCI-release/releases)
and download the file for your operating system:

| Platform | Artifact |
|----------|----------|
| Windows  | `PyBCI-<version>-windows-x64.zip` |
| macOS (Apple Silicon) | `PyBCI-<version>-macos-arm64.dmg` (or `.zip`) |
| Linux    | `PyBCI-<version>-linux-x64.tar.gz` |

## Install

See [INSTALL.md](INSTALL.md) for per-OS install and first-launch steps.

## Optional verification

Each release includes `SHA-256SUMS`. Most early-access users do not need to
verify manually. Technical users can confirm a download matches the published
checksum — see [VERIFY.md](VERIFY.md).

## Support

Questions or problems: [hello@efferentsystems.com](mailto:hello@efferentsystems.com?subject=PyBCI%20help).
When reporting an issue, include the PyBCI version, your operating system, the
step that failed, and the exact error text. Do not include API keys, secrets, or
private recording data.

## Project background

[Prithviraj Mody's engineering portfolio](https://github.com/prithvirajmody/prithvirajmody.github.io#readme) includes the supporting hardware-free regression harness and related neurotechnology work.
