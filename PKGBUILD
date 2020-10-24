# Maintainer: Andrew Sun <adsun701@gmail.com>
# Contributor: Maxime Gauduin <alucryd@archlinux.org>
# Contributor: josephgbr <rafael.f.f1@gmail.com>
# Contributor: Maribu <leonidas200@web.de>

pkgname=lib32-gdbm
pkgver=1.18.1
pkgrel=1
pkgdesc='GNU database library (32-bit)'
arch=('x86_64')
url='http://www.gnu.org/software/gdbm/gdbm.html'
license=('GPL')
depends=('gdbm' 'lib32-glibc')
makedepends=('gcc-multilib' 'lib32-gcc-libs')
source=("ftp://ftp.gnu.org/gnu/gdbm/gdbm-${pkgver}.tar.gz" "parseopt-fix.patch")
options=('!makeflags')
sha256sums=('86e613527e5dba544e73208f42b78b7c022d4fa5a6d5498bf18c8d6f745b91dc')

build() {
  cd gdbm-${pkgver}

  export CC='gcc -m32'
  export CXX='g++ -m32'
  export PKG_CONFIG_PATH='/usr/lib32/pkgconfig'

  ./configure \
    --prefix='/usr' \
    --libdir='/usr/lib32' \
    --enable-libgdbm-compat
  make
}

package() {
  cd gdbm-${pkgver}

  make DESTDIR="${pkgdir}" install
  rm -rf "${pkgdir}"/usr/{bin,share,include}
}

prepare() {
    cd "$srcdir/"gdbm"-$pkgver"
    patch --forward --strip=1 --input="${srcdir}/parseopt-fix.patch"
}

# vim: ts=2 sw=2 et:

sha256sums=('86e613527e5dba544e73208f42b78b7c022d4fa5a6d5498bf18c8d6f745b91dc'
            'fe86ffdd280bededc0ca4afe6e39c0107c07ea2590bbf3e2e6f9dd0638159e21')
