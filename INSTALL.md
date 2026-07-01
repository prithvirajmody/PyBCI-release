# Install PyBCI (Early Access)

PyBCI ships as a packaged app that bundles its runtime — no Python setup
required. Download it from the
[Releases page](https://github.com/prithvirajmody/PyBCI-release/releases).

> **Early access — unsigned build.** Windows and macOS may show an "unknown
> publisher", "unidentified developer", or SmartScreen-style warning because
> code-signing certificates are still being provisioned. **Only continue if you
> received this download directly from the PyBCI team.**

## 1. Before downloading

PyBCI release artifacts support x64 Windows, macOS, and Linux. Allow enough disk
space for the application, projects, recordings, and generated models. Install
the vendor drivers required by your EEG board before connecting hardware. An AI
provider key is optional; an OpenAI key can be entered during first launch.

## 2. Windows

1. Download `PyBCI-<version>-windows-x64.zip`.
2. Right-click the ZIP and choose **Extract All**, extracting to a
   user-writable folder.
3. Open the extracted `PyBCI` folder and run `PyBCI.exe`.
4. If SmartScreen shows "Windows protected your PC", this is expected for an
   unsigned early-access build. Only continue (More info → Run anyway) if you
   received this from the PyBCI team.

## 3. macOS

1. Download `PyBCI-<version>-macos-x64.dmg` (or the `.zip` if the notes direct
   you to it).
2. Open the DMG and copy `PyBCI.app` to Applications.
3. Launch `PyBCI.app`. If macOS says it "cannot be opened because the developer
   cannot be verified", this is expected for an unsigned early-access build.
   Only if you trust the source, open **System Settings → Privacy & Security**
   and choose **Open Anyway**.

## 4. Linux

1. Download `PyBCI-<version>-linux-x64.tar.gz`.
2. Extract it: `tar -xzf PyBCI-<version>-linux-x64.tar.gz`
3. Launch `PyBCI/PyBCI`. The executable may need run permission:
   `chmod +x PyBCI/PyBCI`.

## 5. First launch

The setup wizard asks for a writable projects directory and can optionally save
an OpenAI API key in the local PyBCI environment file. Review the environment
check before continuing. PyBCI then creates or validates the projects directory
and starts its loopback-only local service.

## 6. Security

> PyBCI runs custom preprocessing scripts, Record Code mode, and local/developer
> plugins without a sandbox, using your account's permissions. Hosted marketplace
> packages are accepted only after signature verification; that verification does
> not cover shared projects, local plugins, Code mode scripts, or app-update
> metadata. Treat shared projects and plugins as executable code and use them
> only when you trust their source.

## 7. Updating and uninstalling

Auto-update is not enabled during early access. To update, close PyBCI, download
the newer early-access build, and replace the extracted app or application
bundle. Keep the projects directory separate from the application so updating
does not remove projects.

To uninstall, close PyBCI and remove the extracted application or `PyBCI.app`.
User settings and plugins remain under `~/.pybci/`, and projects remain in the
projects directory selected during setup. Remove those locations only if you also
intend to delete that data.

## 8. Optional verification

`SHA-256SUMS` is included with each release for technical users who want to
confirm their download. See [VERIFY.md](VERIFY.md). This is optional for
early-access users.

## 9. Troubleshooting / help

Email [hello@efferent.systems](mailto:hello@efferent.systems?subject=PyBCI%20help)
with your PyBCI version, OS, the failing step, and the exact error text. Do not
include API keys, secrets, or private recording data.
