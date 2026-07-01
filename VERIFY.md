# Verify a PyBCI release

Always verify an artifact before opening it. Download `SHA-256SUMS` from the same
release, confirm the checksum, then verify the platform signature.

> **Release-signing GPG fingerprint:** `UNPROVISIONED — publish the production
> fingerprint here and on efferent.systems before the first public release.`
>
> The `PyBCI-release-signing-public.asc` file shipped beside a release is
> convenient key material, but is **not** a trust anchor by itself — always
> compare its fingerprint against the value published above and on the website.

## Checksums (all platforms)

From the folder containing the downloaded artifact(s) and `SHA-256SUMS`:

```bash
# macOS / Linux
sha256sum --check SHA-256SUMS        # Linux
shasum -a 256 -c SHA-256SUMS         # macOS
```

```powershell
# Windows (PowerShell) — compare against the matching line in SHA-256SUMS
Get-FileHash .\PyBCI-<version>-windows-x64.zip -Algorithm SHA256
```

## macOS

Verify the app before launch and verify the stapled notarization ticket on both
payload types:

```bash
codesign --verify --deep --strict --verbose=2 PyBCI.app
spctl --assess --type execute --verbose=4 PyBCI.app
xcrun stapler validate PyBCI.app
codesign --verify --deep --strict --verbose=2 PyBCI-*-macos-x64.dmg
spctl --assess --type open --context context:primary-signature --verbose=4 PyBCI-*-macos-x64.dmg
xcrun stapler validate PyBCI-*-macos-x64.dmg
```

## Windows

Verify every executable or installer:

```powershell
Get-AuthenticodeSignature .\PyBCI\PyBCI.exe | Format-List
signtool verify /pa /all /v .\PyBCI\PyBCI.exe
```

`Get-AuthenticodeSignature` must report `Status: Valid`. Repeat for any shipped
`.exe`, `.msi`, or installer files.

## Linux

First compare the imported key fingerprint with the independently published
fingerprint above, then verify checksums and the detached signatures:

```bash
gpg --import PyBCI-release-signing-public.asc
gpg --fingerprint
sha256sum --check SHA-256SUMS
gpg --verify PyBCI-*-linux-x64.tar.gz.asc PyBCI-*-linux-x64.tar.gz
gpg --verify SHA-256SUMS.asc SHA-256SUMS
```

## If verification fails

Do not run the artifact. Re-download from the official
[Releases page](https://github.com/prithvirajmody/PyBCI-release/releases) over a
trusted network, and if it still fails, report it to
[info@efferent.systems](mailto:info@efferent.systems?subject=PyBCI%20signature%20verification)
with the artifact name, version, and the exact command output.
