# Contributor: Andrea Scarpino <andrea@archlinux.org>

pkgname=baloo-widgets-frameworks-git
pkgver=r364.2ecd544
pkgrel=1
pkgdesc="A framework for searching and managing metadata"
arch=('i686' 'x86_64')
url='https://projects.kde.org/projects/kde/kdelibs/baloo'
license=('LGPL')
depends=('baloo-git')
makedepends=('extra-cmake-modules' 'git' 'kdoctools')
source=('git://anongit.kde.org/baloo-widgets#branch=frameworks')
md5sums=('SKIP')

pkgver() {
  cd baloo-widgets
  printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

prepare() {
  mkdir -p build
}

build() {
  cd build
  cmake ../baloo-widgets \
    -DCMAKE_BUILD_TYPE=Release \
    -DCMAKE_INSTALL_PREFIX=/opt/kf5 \
    -DCMAKE_PREFIX_PATH=/opt/kf5 \
    -DLIB_INSTALL_DIR=lib
  make
}

package() {
  cd build
  make DESTDIR="${pkgdir}" install
}
