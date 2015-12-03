
pkgname=opendungeons
_pkgname=OpenDungeons
pkgver=0.6.0
pkgrel=1
pkgdesc="Open source game inspired by Dungeon Keeper"
url="https://github.com/OpenDungeons/OpenDungeons"
arch=('x86_64')
license=('zlib')
depends=('ogre' 'boost' 'boost-libs' 'cegui' 'sfml')
makedepends=('mesa' 'cmake')
source=("https://github.com/OpenDungeons/OpenDungeons/archive/${pkgver}.tar.gz")
md5sums=('f86e24d8d59afa15ad656d0d55450bde')

build() {
  cd ${_pkgname}-${pkgver}
  mkdir -p build
  cd build
  
  cmake .. \
    -DCMAKE_INSTALL_PREFIX=/usr \
    -DCMAKE_BUILD_TYPE=Release \
    -DOD_BIN_PATH=/usr/bin \
    -DOD_PLUGINS_CFG_PATH=/etc \
    -DOD_DATA_PATH=/usr/share/games \
    -DOD_SHARE_PATH=/usr/share
  make
}

package() {
  cd ${_pkgname}-${pkgver}/build
  
  make DESTDIR=${pkgdir} install
}
