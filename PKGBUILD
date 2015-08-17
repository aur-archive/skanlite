# Maintainer: birdflesh <antkoul at gmail dot com>
# Contributor: Andrea Scarpino <andrea@archlinux.org>
# Contributor: Pierre Schmitz <pierre@archlinux.de>

pkgname=skanlite
pkgver=1.1
pkgrel=1
pkgdesc="Image Scanning Application for KDE"
arch=('i686' 'x86_64')
url='http://www.kde.org/applications/graphics/skanlite'
license=('GPL')
depends=('kdebase-runtime' 'libksane')
makedepends=('cmake' 'automoc4')
source=("http://download.kde.org/stable/$pkgname/$pkgver/src/$pkgname-$pkgver.tar.xz")
md5sums=('21cd642d4177fff759bf4694af39b9fe')

build() {
  cd "$srcdir"
  mkdir build
  cd build
  cmake ../$pkgname-$pkgver \
    -DQT_QMAKE_EXECUTABLE=qmake-qt4 \
    -DCMAKE_BUILD_TYPE=Release \
    -DCMAKE_INSTALL_PREFIX=/usr
  make
}

package() {
  cd "$srcdir/build"
  make DESTDIR="$pkgdir" install
}
