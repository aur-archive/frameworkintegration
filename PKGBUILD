# Maintainer: Andrea Scarpino <andrea@archlinux.org>

pkgname=frameworkintegration
pkgver=4.99.0
pkgrel=1
pkgdesc='Framework providing components to allow applications to integrate with a KDE Workspace'
arch=('i686' 'x86_64')
url='https://projects.kde.org/projects/frameworks/frameworkintegration'
license=('LGPL')
depends=('attica-qt5' 'kio' 'kbookmarks')
makedepends=('extra-cmake-modules')
groups=('kf5')
source=("http://download.kde.org/unstable/frameworks/${pkgver}/${pkgname}-${pkgver}.tar.xz")
md5sums=('7d10b581c89019857373508454c8c3ab')

prepare() {
  mkdir -p build
}

build() {
  cd build
  cmake ../${pkgname}-${pkgver} \
    -DCMAKE_BUILD_TYPE=Release \
    -DCMAKE_INSTALL_PREFIX=/opt/kf5 \
    -DLIB_INSTALL_DIR=lib \
    -DBUILD_TESTING=OFF
  make
}

package() {
  cd build
  make DESTDIR="${pkgdir}" install
}
