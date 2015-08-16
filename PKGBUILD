# $Id: PKGBUILD 55504 2011-09-13 21:15:39Z ebelanger $
# Contributor: William Rea <sillywilly@gmail.com>
# Maintainer: Daniel J Griffiths <ghost1227@archlinux.us>

pkgname=mms_client
pkgver=0.0.3
pkgrel=5
pkgdesc="mms protocol download utility"
arch=('i686' 'x86_64')
url="http://ole.tange.dk/projekter/kontroversielt/www.geocities.com/majormms/"
license=('GPL')
depends=('glibc')
#source=(http://ole.tange.dk/projekter/kontroversielt/www.geocities.com/majormms/mms_client-0.0.3.tar.gz
source=(http://web.archive.org/web/20071011022352/http://geocities.com/majormms/mms_client-0.0.3.tar.gz
	mmsclient-0.0.3-fbsd.patch \
	mmsclient-0.0.3-r1.patch)
md5sums=('c91171a0bbbfb94290d362e907432787'
         '8b1f4c95b4b13abd91d2c7c4ba51ea23'
         'b85485058a26b3a0881639bc02de71cb')

build() {
	cd "${srcdir}/${pkgname}-${pkgver}"
	patch -p0 -i ../mmsclient-0.0.3-fbsd.patch
	patch -p1 -i ../mmsclient-0.0.3-r1.patch
	./configure --prefix=/usr
	make
}

package() {
	cd "${srcdir}/${pkgname}-${pkgver}"
	make DESTDIR="${pkgdir}" install
}
