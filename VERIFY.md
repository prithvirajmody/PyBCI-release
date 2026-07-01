# Optional verification (Early Access)

> **Early access — unsigned build.** These builds are **not code-signed**, so
> there are no Authenticode, Apple notarization, or GPG signatures to verify yet.
> Only the SHA-256 checksum below is available. Signature verification will be
> documented here when the signed 1.0.0 production release ships.

Manual verification is **optional** for early-access users. It is provided for
researchers and developers who want to independently confirm that their
downloaded file matches the published release artifact.

## Checksums (all platforms)

Download `SHA-256SUMS` from the same release, into the folder containing the
downloaded artifact(s):

```bash
# Linux
sha256sum --check SHA-256SUMS
```

```bash
# macOS
shasum -a 256 -c SHA-256SUMS
```

```powershell
# Windows (PowerShell) — compare against the matching line in SHA-256SUMS
Get-FileHash .\PyBCI-<version>-windows-x64.zip -Algorithm SHA256
```

Each output line should read `OK`, or the hash should match the matching line in
`SHA-256SUMS`.

## If verification fails

Do not run the artifact. Re-download from the official
[Releases page](https://github.com/prithvirajmody/PyBCI-release/releases) over a
trusted network, and if it still fails, report it to
[hello@efferent.systems](mailto:hello@efferent.systems?subject=PyBCI%20checksum)
with the artifact name, version, and the exact command output.
