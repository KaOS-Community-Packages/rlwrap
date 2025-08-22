pkgname=rlwrap
pkgver=0.47.1
pkgrel=1
pkgdesc="A readline wrapper for programs with history"
arch=('x86_64')
url="http://utopia.knoware.nl/~hlub/uck/rlwrap/"
license=('unknown')
depends=('gawk' 'perl')
makedepends=('gcc')
source=("https://github.com/hanslub42/${pkgname}/archive/refs/tags/v${pkgver}.tar.gz")
md5sums=('edf41a6d9457432c6e4d62bb418e7c14')

prepare() {
	cd ${pkgname}-${pkgver}
	if [[ ! -e configure ]]; then
		aclocal
		autoconf
		autoheader
		[ -e tools ] || mkdir tools
		automake --add-missing
	fi
}

build() {
	cd ${pkgname}-${pkgver}
	./configure --prefix=/usr --without-libptytty
	make
}

package() {
	cd ${pkgname}-${pkgver}
	make install DESTDIR="${pkgdir}"
}
