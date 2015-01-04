pkgname=rlwrap
pkgver=0.42
pkgrel=1
pkgdesc="A readline wrapper for programs with history"
arch=('x86_64')
url="http://utopia.knoware.nl/~hlub/uck/rlwrap/"
license=('unknown')
depends=('gawk' 'perl')
makedepends=('gcc')
source=("https://github.com/hanslub42/${pkgname}/archive/v${pkgver}.tar.gz")
md5sums=('6db341971cdb8bedfecf0a293e7cfff4')

build() {
	cd ${pkgname}-${pkgver}
	./configure --prefix=/usr
	make
}

package() {
	cd ${pkgname}-${pkgver}
	make install DESTDIR="${pkgdir}"
}
