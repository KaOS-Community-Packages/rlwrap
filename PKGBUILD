pkgname=rlwrap
pkgver=0.45.1
pkgrel=1
pkgdesc="A readline wrapper for programs with history"
arch=('x86_64')
url="http://utopia.knoware.nl/~hlub/uck/rlwrap/"
license=('unknown')
depends=('gawk' 'perl')
makedepends=('gcc')
source=("https://github.com/hanslub42/${pkgname}/archive/v${pkgver}.tar.gz")
md5sums=('299b137baba2174cd2f73e6c3070ae8d')

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
	./configure --prefix=/usr
	make
}

package() {
	cd ${pkgname}-${pkgver}
	make install DESTDIR="${pkgdir}"
}
