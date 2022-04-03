#!/bin/bash

# Disable various shellcheck rules that produce false positives in this file.
# Repository rules should be added to the .shellcheckrc file located in the
# repository root directory, see https://github.com/koalaman/shellcheck/wiki
# and https://archiv8.github.io for further information.
# shellcheck disable=SC2034,SC2154
# [ToDo]: Add files: User documentation
# [ToDo]: Add files: Tooling
# [FixMe]: Namcap warnings and errors

# Maintainer: Ross Clark <archiv8@artisteducator.com>
# Contributor: Ross Clark <archiv8@artisteducator.com>



pkgbase=patool
pkgname="patool"
pkgver=1.12
pkgrel=5
pkgdesc="Portable command line archive file manager"
arch=("any")
url="https://wummel.github.io/patool/"
license=("GPL")
depends=(
    # Official Arch Linux repositories
    "python"
  )
makedepends=(
    # Official Arch Linux repositories
    "python-setuptools"
    )
optdepends=(
    # Official Arch Linux repositories
    "p7zip: extracting ZIP and 7z files"
    "tar: extracting TAR files"
    "unrar: extracting RAR files"
    )
#source=("https://pypi.python.org/packages/source/p/$pkgbase/$pkgbase-$pkgver.tar.gz")
source=(
  "$pkgbase-$pkgver.tar.gz::https://github.com/wummel/patool/archive/upstream/${pkgver}.tar.gz"
  )
sha256sums=(
  "582fd4b87c263325958c1550400504799018c88bc3444f249bba304ae1747f1f"
  )


build() {
  cd "${pkgbase}-upstream-${pkgver}"
  python setup.py build
}

package() {
  cd "${pkgbase}-upstream-${pkgver}"
  python setup.py install --root=$pkgdir --prefix=/usr --optimize=1 --skip-build
}
