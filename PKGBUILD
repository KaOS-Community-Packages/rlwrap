pkgname=rlwrap
pkgver=0.43.0
pkgrel=1
_snapshot='-snapshot.july19.2016'
pkgdesc="A readline wrapper for programs with history"
arch=('x86_64')
url="http://utopia.knoware.nl/~hlub/uck/rlwrap/"
license=('unknown')
depends=('gawk' 'perl')
makedepends=('gcc')
source=("https://github.com/hanslub42/${pkgname}/archive/${pkgver}${_snapshot}.tar.gz")
md5sums=('9e77cceb861648fb1425a387b0ba9a3c')

prepare() {
	cd ${pkgname}-${pkgver}${_snapshot}
	if [[ ! -e configure ]]; then
		aclocal
		autoconf
		autoheader
		[ -e tools ] || mkdir tools
		automake --add-missing
	fi
}

build() {
	cd ${pkgname}-${pkgver}${_snapshot}
	./configure --prefix=/usr
	make
}

package() {
	cd ${pkgname}-${pkgver}${_snapshot}
	make install DESTDIR="${pkgdir}"
}
