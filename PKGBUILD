# Maintainer: Hec <hec@heccraft.com>

_pkgname=dmenu
pkgname=$_pkgname-hec-git
pkgver=5.0
pkgrel=1
pkgdesc="A generic menu for X, patched for centering, borders, numbers, line height, and fuzzy matching/highlighting"
url="http://tools.suckless.org/dmenu/"
arch=('i686' 'x86_64')
license=('MIT')
depends=('sh' 'libxinerama' 'libxft' 'ttf-jetbrains-mono' 'ttf-joypixels')
makedepends=('git')
provides=($_pkgname)
conflicts=($_pkgname)
source=(git+https://github.com/hecknt/dmenu)
sha256sums=('SKIP')

pkgver() {
  cd $_pkgname
  git describe --tags --long | sed 's/-/./g'
}

build(){
  cd $_pkgname
  make \
    X11INC=/usr/include/X11 \
    X11LIB=/usr/lib/X11
}

package() {
  cd $_pkgname
  make PREFIX=/usr DESTDIR="$pkgdir" install
  install -Dm644 LICENSE "$pkgdir"/usr/share/licenses/$pkgname/LICENSE
}