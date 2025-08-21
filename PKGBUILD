pkgname=rlwrap
pkgver=0.47
pkgrel=1
pkgdesc="A readline wrapper for programs with history"
arch=('x86_64')
url="http://utopia.knoware.nl/~hlub/uck/rlwrap/"
license=('unknown')
depends=('gawk' 'perl')
makedepends=('gcc')
source=("https://github.com/hanslub42/${pkgname}/archive/refs/tags/v${pkgver}.tar.gz")
md5sums=('98634af12663f89ce9665bffda5d5a4d')

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
