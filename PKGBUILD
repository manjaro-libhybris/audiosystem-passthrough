# Maintainer: Bardia Moshiri <fakeshell@bardia.tech>

pkgname=audiosystem-passthrough
provides=('audiosystem-passthrough')
_pkgbase=audiosystem-passthrough
pkgver=35.cd73fcc
pkgrel=2
arch=('armv7h' 'aarch64' 'x86' 'x86_64')
url="https://github.com/mer-hybris/audiosystem-passthrough"
license=('BSD')
depends=()
makedepends=('git' 'pkgconfig' 'libgbinder' 'automake' 'autoconf' 'systemd')
source=("audiosystem-passthrough::git+https://github.com/mer-hybris/audiosystem-passthrough.git"
	"audiosystem-passthrough.service")
md5sums=('SKIP'
	 'SKIP')
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

  mkdir -p "${pkgdir}/usr/lib/systemd/user/"
  install -Dm644 "${srcdir}/audiosystem-passthrough.service" "${pkgdir}/usr/lib/systemd/user/audiosystem-passthrough.service"
}
