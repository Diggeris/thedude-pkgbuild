# Maintainer: Diggeris
# Contributor: Marco Steiger <marco (at) steiger (dot) online>
pkgname=thedude
pkgver=7.24.1
pkgrel=2
pkgdesc="MikroTik The Dude network monitoring client"
url="https://mikrotik.com"
arch=('x86_64')
license=('custom')
makedepends=('7zip')
depends=('findutils' 'wine')
optdepends=(
  'ttf-ms-fonts: for better fonts'
)
source=("${pkgname}-${pkgver}.exe::https://download.mikrotik.com/routeros/${pkgver}/dude-install-${pkgver}.exe"
        "${pkgname}.desktop"
        "${pkgname}.png"
        "${pkgname}")
sha256sums=('28c37a9e22d8efcdef7f34045b72a7cf3db66273bd884418e14e5b95bc0fd957'
            '53d1fa8fa8cd676572c6c7ec9daa6ad7ea7d1ff4f35b2e557d64d47d7622e602'
            'b2595e2c2c9980fd5a9b2a6bbd847a8cbb158a4c18e36e9002ccbec109b4eaa1'
            'e2c31fa283796f4e9a47d5c886fe28f2021c38268e000beca8dff4e4f37d8db9')

build() {
  rm -rf "${srcdir}/${pkgname}-src"
  mkdir -p "${srcdir}/${pkgname}-src"
  7z e -y -o"${srcdir}/${pkgname}-src/" "${srcdir}/${pkgname}-${pkgver}.exe"
}

package() {
  mkdir -p "${pkgdir}/usr/share/${pkgname}/"
  cp -a "${srcdir}/${pkgname}-src/." "${pkgdir}/usr/share/${pkgname}/"
  chmod -R u=rwX,go=rX "${pkgdir}/usr/share/${pkgname}"
  install -Dm755 "${srcdir}/${pkgname}" "${pkgdir}/usr/bin/${pkgname}"
  install -Dm644 "${srcdir}/${pkgname}.png" "${pkgdir}/usr/share/pixmaps/${pkgname}.png"
  install -Dm644 "${srcdir}/${pkgname}.desktop" "${pkgdir}/usr/share/applications/${pkgname}.desktop"
}
