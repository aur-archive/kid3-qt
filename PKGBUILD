# Maintainer: Alessio Sergi <asergi at archlinux dot us>
# Contributor: anubis2591 <anubis2591 at gmail dot com>

pkgname=kid3-qt
pkgver=3.0.2
pkgrel=1
pkgdesc="An efficient ID3 tag editor - Non KDE version"
arch=('i686' 'x86_64')
url="http://kid3.sourceforge.net"
license=('GPL2')
depends=('chromaprint' 'id3lib' 'qt4' 'taglib')
makedepends=('cmake' 'docbook-xsl')
install="$pkgname".install
source=("http://downloads.sourceforge.net/kid3/kid3-${pkgver}.tar.gz")
sha1sums=('cc6387a18e304fa7b7bcc377e7408ce07bccea01')

prepare() {
  mkdir "$srcdir"/build
}

build() {
  cd "$srcdir"/build
  cmake ../kid3-"$pkgver" \
    -DCMAKE_INSTALL_PREFIX=/usr \
    -DCMAKE_BUILD_TYPE=Release \
    -DQT_QMAKE_EXECUTABLE=qmake-qt4 \
    -DWITH_APPS=Qt \
    -DWITH_PHONON=OFF
  make
}

package() {
  cd "$srcdir"/build
  make DESTDIR="$pkgdir" install
}
