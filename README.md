# MikroTik The Dude PKGBUILD

Up-to-date PKGBUILD for MikroTik The Dude on Arch Linux.

This repository provides an unofficial Arch Linux package for MikroTik The Dude and automatically tracks new MikroTik stable releases.

## Installation

Clone the repository:

```bash
git clone https://github.com/Diggeris/thedude-pkgbuild.git
cd thedude-pkgbuild
```

Build and install the package:

```bash
makepkg -si
```

## Automatic updates

GitHub Actions checks for a new MikroTik stable release every Monday at 01:00 Europe/Vilnius time.

When a new version is detected, the workflow automatically:

- Downloads the official MikroTik The Dude installer
- Calculates the SHA256 checksum
- Updates `pkgver` in `PKGBUILD`
- Updates the installer SHA256 checksum
- Regenerates `.SRCINFO`
- Performs a full package build test
- Opens a Pull Request with the changes

Updates are not automatically merged into `main`.

## Pull requests

Pull requests are automatically checked before merging.

The CI workflow:

- Verifies that `.SRCINFO` matches `PKGBUILD`
- Performs a full Arch Linux package build

## Package origin

This package is based on the existing AUR `thedude` package.

Original package maintainer:

- Marco Steiger

The original maintainer is preserved as a contributor in `PKGBUILD`.

## Disclaimer

This is an unofficial community project and is not affiliated with or endorsed by MikroTik.

MikroTik and The Dude are trademarks and/or products of MikroTik.

This repository does not redistribute the MikroTik The Dude installer. The installer is downloaded directly from MikroTik during the package build process.
