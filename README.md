# Web3MovieTrack — installers

Release binaries for the Web3MovieTrack desktop app, which installs and runs as
**MovioHD**. This repository holds build output and nothing else: no source, no
issue tracker use, no pull requests. The app's front door is
[moviohd.pages.dev](https://moviohd.pages.dev) — that site has the catalogue and
the download buttons; this page is where those buttons land.

## Current releases

Every file is published under the newest release, so
`/releases/latest/download/<file>` is a permanent link that survives new
versions. Pick the one that matches your machine:

| File | For | Install |
|---|---|---|
| `MovioHD-Setup-x64.exe` | Windows 10 and 11, 64-bit | Double-click, then **Yes** at the prompt. Sets up for the current user; no administrator rights needed. |
| `MovioHD-win-x64.zip` | Windows 10 and 11, 64-bit | Unzip anywhere and run `MovioHD.exe`. Nothing is written to the system. |

Linux packages — `.deb`, `.rpm` and an AppImage — are published here as they are
built. Until they appear, the two Windows files above are the only downloads.

## Before you install

**SmartScreen.** The installer is not code-signed, so Windows shows
"Windows protected your PC" the first time. Choose **More info → Run anyway**.
Code signing is a paid certificate that is not in place yet; the warning is
expected and is not evidence that the download was tampered with.

**Verify the download.** The SHA-256 of every file is listed in that release's
notes. After downloading:

```powershell
Get-FileHash .\MovioHD-Setup-x64.exe -Algorithm SHA256
```

```sh
sha256sum MovioHD-Setup-x64.exe
```

The hash must match the one on the release page. A truncated download is the
usual reason for a mismatch, and re-downloading fixes it.

## Command-line install

```powershell
curl -fsSL https://moviohd.pages.dev/install.ps1 | pwsh -Command '-'
```

`install.ps1` fetches `MovioHD-Setup-x64.exe` from the newest release here and
runs it. It is the same download the site's Windows button offers.

## License

The application is released under the MIT license — see [LICENSE](LICENSE).
These are unmodified builds. No source is published in this repository, and no
trademark rights are granted.
