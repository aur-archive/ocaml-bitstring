# Maintainer: Patryk Kowalczyk < patryk at kowalczyk dot ws>
# Contributor: Serge Zirukin <ftrvxmtrx@gmail.com>
# Contributor: Sergei Lebedev <superbobry@gmail.com>
# Contributor: Pierre Bourdon <delroth@gmail.com>

pkgname=ocaml-bitstring
pkgver=2.0.4
pkgrel=2
pkgdesc="An OCaml library for Erlang-style bit patterns."
arch=('i686' 'x86_64')
license=('GPL2')
url="http://code.google.com/p/bitstring/"
depends=('ocaml')
makedepends=('time' 'ocaml-findlib')
source=("http://bitstring.googlecode.com/files/$pkgname-$pkgver.tar.gz")
md5sums=('88ad0ee29af8b077e63896da23ec9054')
options=(!makeflags !strip)

build() {
  cd "$srcdir/$pkgname-$pkgver"

  ./configure --prefix=/usr
  make all doc
}

package() {
  cd "$srcdir/$pkgname-$pkgver"
  export OCAMLFIND_DESTDIR="$pkgdir$(ocamlfind printconf destdir)"
  install -dm 755 "$OCAMLFIND_DESTDIR/stublibs"
  make install
  install -d -m 0755 "${pkgdir}/usr/share/doc/$pkgname"
  install -t "${pkgdir}/usr/share/doc/$pkgname/" html/*
  install -Dm 644 COPYING "$pkgdir/usr/share/licenses/$pkgname/COPYING"
}
md5sums=('5f92601000aea467c989afe141cb1632')
