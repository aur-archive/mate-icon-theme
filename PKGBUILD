# Maintainer : Martin Wimpress <code@flexion.org>
# Contributor: Giovanni "Talorno" Ricciardi <kar98k.sniper@gmail.com>
# Contributor: Xpander <xpander0@gmail.com>

pkgname=mate-icon-theme
pkgver=1.6.3
pkgrel=1
pkgdesc="MATE icon theme"
url="http://mate-desktop.org"
arch=('any')
license=('GPL')
depends=('hicolor-icon-theme' 'gtk-update-icon-cache' 'librsvg')
makedepends=('icon-naming-utils' 'mate-common' 'perl-xml-parser')
options=(!emptydirs !strip)
groups=('mate')
source=("http://pub.mate-desktop.org/releases/1.6/${pkgname}-${pkgver}.tar.xz")
sha1sums=('e7d2f4060e3b6233c2e37ccef93f40bde53b2873')
install=${pkgname}.install

build() {
    cd "${srcdir}/${pkgname}-${pkgver}"
    ./configure \
        --prefix=/usr
    make
}

package() {
    cd "${srcdir}/${pkgname}-${pkgver}"
    make DESTDIR="${pkgdir}" install
    rm -f "${pkgdir}/usr/share/icons/mate/icon-theme.cache"
}
