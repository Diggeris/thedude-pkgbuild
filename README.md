<!-- SPDX-FileCopyrightText: 2026 Diggeris -->
<!-- SPDX-License-Identifier: 0BSD -->
# MikroTik The Dude PKGBUILD

[![PR package check](https://github.com/Diggeris/thedude-pkgbuild/actions/workflows/pr-build.yml/badge.svg)](https://github.com/Diggeris/thedude-pkgbuild/actions/workflows/pr-build.yml)
[![Version check](https://github.com/Diggeris/thedude-pkgbuild/actions/workflows/check-version.yml/badge.svg)](https://github.com/Diggeris/thedude-pkgbuild/actions/workflows/check-version.yml)

Up-to-date PKGBUILD for MikroTik The Dude on Arch Linux.

This repository provides an unofficial Arch Linux package for MikroTik The Dude and automatically tracks new MikroTik releases that include an updated The Dude build.

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

## Tested on

The package is tested automatically in an Arch Linux environment and has also been manually tested on Manjaro Linux.

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

## License

Documentation and GitHub Actions automation created for this repository are licensed under the BSD Zero Clause License (`0BSD`).

Files derived from the original AUR `thedude` package are not relicensed by this repository and retain their original authorship and applicable terms.
