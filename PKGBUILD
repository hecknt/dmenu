# Maintainer: Hec <hec@heccraft.com>

_pkgname=dmenu
pkgname=$_pkgname-hec-git
pkgver=5.0.r3.77d7b28
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
	cd "${_pkgname}"
    printf "5.0.r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

build(){
  cd $_pkgname
  make \
    X11INC=/usr/include/X11 \
    X11LIB=/usr/lib/X11
}

package() {
  cd $_pkgname
  mkdir -p "$pkgdir"/opt/"$pkgname"
  cp -rf * "$pkgdir"/opt/"$pkgname"
  make PREFIX=/usr DESTDIR="$pkgdir" install
  install -Dm644 LICENSE "$pkgdir"/usr/share/licenses/$pkgname/LICENSE
}
