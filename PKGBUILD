#Maintainer Erik Inkinen <erik.inkinen@gmail.com>
pkgname=audiosystem-passthrough
provides=('audiosystem-passthrough')
_pkgbase=audiosystem-passthrough
pkgver=9902.09074dc0
pkgrel=1
arch=('armv7h' 'aarch64' 'x86' 'x86_64')
url="https://github.com/mer-hybris/audiosystem-passthrough"
license=('BSD')
depends=()
makedepends=('git' 'pkgconfig' 'libgbinder' 'automake' 'autoconf' 'systemd')
source=("audiosystem-passthrough::git+https://github.com/mer-hybris/audiosystem-passthrough.git")
md5sums=('SKIP')
options=(debug !strip)

pkgver() {
  cd "${srcdir}/${_pkgbase}"
  echo $(git rev-list --count HEAD).$(git rev-parse --short HEAD)
}

build() {
  cd "${srcdir}/${_pkgbase}"
  make KEEP_SYMBOLS=1 all
}

package() {
  cd "${srcdir}/${_pkgbase}"
  make DESTDIR="$pkgdir" install
}

