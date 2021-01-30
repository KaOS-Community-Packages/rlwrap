pkgname=rlwrap
pkgver=0.44
pkgrel=1
pkgdesc="A readline wrapper for programs with history"
arch=('x86_64')
url="http://utopia.knoware.nl/~hlub/uck/rlwrap/"
license=('unknown')
depends=('gawk' 'perl')
makedepends=('gcc')
source=("https://github.com/hanslub42/${pkgname}/releases/download/7c1e432/${pkgname}-${pkgver}.tar.gz")
md5sums=('21013e5db76f0b052ab2bdb69159d3ad')

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
