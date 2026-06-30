# Install PyBCI

PyBCI ships as a signed packaged app that bundles its runtime — no Python setup
required. Download it from the
[Releases page](https://github.com/prithvirajmody/PyBCI-release/releases) or from
[efferent.systems/download](https://efferent.systems/download).

## 1. Before downloading

PyBCI release artifacts support x64 Windows, macOS, and Linux. Allow enough disk
space for the application, projects, recordings, and generated models. Install
the vendor drivers required by your EEG board before connecting hardware. An AI
provider key is optional; an OpenAI key can be entered during first launch.

## 2. Download and verify

Download PyBCI only from the official Releases page or website. Use only
artifacts identified as signed releases; files labeled `unsigned` are CI outputs
and are not public distributions. Download `SHA-256SUMS` and compare the checksum
before opening the archive, and verify the platform signature. Detailed
verification commands are in [VERIFY.md](VERIFY.md).

## 3. Windows

1. Download `PyBCI-<version>-windows-x64.zip` and `SHA-256SUMS`.
2. Verify the SHA-256 checksum and the Authenticode signature on
   `PyBCI\PyBCI.exe` (see [VERIFY.md](VERIFY.md)). The signature status must be
   `Valid`.
3. Extract the ZIP to a user-writable folder.
4. Launch `PyBCI.exe` from the extracted `PyBCI` folder.

## 4. macOS

1. Prefer `PyBCI-<version>-macos-x64.dmg`; use the ZIP only when the release
   notes direct you to it.
2. Verify the SHA-256 checksum, Developer ID signature, Gatekeeper assessment,
   and stapled notarization ticket (see [VERIFY.md](VERIFY.md)).
3. Open the DMG and copy `PyBCI.app` to Applications.
4. Launch `PyBCI.app` from Applications.

Do not bypass Gatekeeper for an artifact that fails verification.

## 5. Linux

1. Download `PyBCI-<version>-linux-x64.tar.gz`, its `.asc` signature,
   `SHA-256SUMS`, and the published PyBCI release-signing public key.
2. Verify the public-key fingerprint against the independently published copy
   (see [VERIFY.md](VERIFY.md)), then verify both the GPG signature and SHA-256
   checksum.
3. Extract the tarball.
4. Launch `PyBCI/PyBCI`. The executable may need run permission:
   `chmod +x PyBCI/PyBCI`.

## 6. First launch

The setup wizard asks for a writable projects directory and can optionally save
an OpenAI API key in the local PyBCI environment file. Review the environment
check before continuing. PyBCI then creates or validates the projects directory
and starts its loopback-only local service.

The diagnostics consent prompt appears on first launch in opt-in regions and in
clinical mode; other regions use an opt-out posture, changeable in Settings.
Remote diagnostics are off by default.

## 7. Security

> PyBCI runs custom preprocessing scripts, Record Code mode, and local/developer
> plugins without a sandbox, using your account's permissions. Hosted marketplace
> packages are accepted only after signature verification; that verification does
> not cover shared projects, local plugins, Code mode scripts, or app-update
> metadata. Treat shared projects and plugins as executable code and use them
> only when you trust their source.

## 8. Updating and uninstalling

To update, close PyBCI, download and verify the newer signed release, then
replace the existing extracted app or application bundle. Keep the projects
directory separate from the application so updating does not remove projects.

To uninstall, close PyBCI and remove the extracted application or `PyBCI.app`.
User settings and plugins remain under `~/.pybci/`, and projects remain in the
projects directory selected during setup. Remove those locations only if you also
intend to delete that data.

## 9. Troubleshooting

- If the app does not launch, re-check the checksum and platform signature,
  extract it to a writable local folder, and verify hardware drivers.
- For signature or notarization failures, use the exact commands in
  [VERIFY.md](VERIFY.md).
- For help, email [hello@efferent.systems](mailto:hello@efferent.systems?subject=PyBCI%20help)
  with your PyBCI version, OS, the failing step, and the error text. Do not
  include API keys, secrets, or private recording data.
