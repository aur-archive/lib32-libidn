_pkgbasename=libidn
pkgname=lib32-$_pkgbasename
pkgver=1.22
pkgrel=1
pkgdesc="Implementation of the Stringprep, Punycode and IDNA specifications (32 bit)"
url="http://www.gnu.org/software/libidn/"
arch=('x86_64')
license=('GPL3' 'LGPL')
depends=('lib32-glibc' "$_pkgbasename>=$pkgver")
makedepends=('gcc-multilib')
options=('!libtool')
source=(http://ftp.gnu.org/gnu/${_pkgbasename}/${_pkgbasename}-${pkgver}.tar.gz)
md5sums=('893a1df0cf3b28b72d248382eaeaca71')

build() {
  cd ${srcdir}/${_pkgbasename}-${pkgver}
  ./configure --prefix=/usr --libdir=/usr/lib32 CC='gcc -m32'
  make
}

package() {
  cd ${srcdir}/${_pkgbasename}-${pkgver}
  make DESTDIR=${pkgdir} install
  rm -rf ${pkgdir}/usr/{bin,include,share}
}
