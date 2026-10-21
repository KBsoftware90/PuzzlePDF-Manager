# PuzzlePDF release distribution

Repository: `KBsoftware90/PuzzlePDF-Manager` (public binaries/distribution only).

Build and validate the application natively on both operating systems. The source
workspace contains `scripts/build-ifw.py` and `scripts/publish-github.py`; the public
repository does not contain application source or private signing keys.

Each release uses tag `vX.Y.Z`. Upload all assets to a **draft** first, check the
installers, then publish the complete release. Do not overwrite a published file.
The publisher refuses public releases with only one native platform package.

## Stable links after the first complete release

- Linux installer: `https://github.com/KBsoftware90/PuzzlePDF-Manager/releases/latest/download/PuzzlePDF-linux-x86_64.run`
- Windows installer: `https://github.com/KBsoftware90/PuzzlePDF-Manager/releases/latest/download/PuzzlePDF-windows-x86_64.exe`
- Linux signed manifest: `https://github.com/KBsoftware90/PuzzlePDF-Manager/releases/latest/download/release-linux-x86_64.json`
- Windows signed manifest: `https://github.com/KBsoftware90/PuzzlePDF-Manager/releases/latest/download/release-windows-x86_64.json`

These links become available after matching assets are published. The website can
keep the installer links unchanged between releases.

## Assets

The packaging tool preserves the normal IFW repository locally and also produces
a flat `github-assets/` directory:

- `PuzzlePDF-<platform>.run` / `.exe`: offline-capable installer.
- `release-<platform>.json`: RSA/SHA-256 signed update manifest.
- `puzzlepdf-<platform>-<sha256-of-relative-path>.bin`: IFW repository files.

The app maps each signed relative path to its flat asset name, downloads it from
`/releases/download/v<signed-version>/`, and restores the nested IFW repository
in a private local staging folder. A new `/latest` release during downloading
does not change the files being downloaded. HTTPS redirects are restricted to the
same repository and the GitHub asset CDN. Signature, platform, expiry and every
file checksum must pass before installation.

## Signing key

`update-public.pem` is a public verification key, safe to distribute. Its private
counterpart remains on the release machine or in a protected secret store. Never
upload private keys, source-workspace archives, `.env` files, account tokens, user
PDFs or vaults. Installer publisher certificates (Windows Authenticode) are a
separate step and are not implied by the signed update manifest.

A native Windows build/install/update check is required before publishing a
Windows package. A Linux build does not produce a Windows executable.
