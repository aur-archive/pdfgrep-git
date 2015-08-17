# Maintainer: thorsten w. <p _at_ thorsten-wissmann.de>
pkgname=pdfgrep-git
pkgver=bef1b23
pkgrel=1
pkgdesc="Grep in pdf-files"
arch=('i686' 'x86_64')
url="http://gitorious.org/pdfgrep/pdfgrep"
license=('GPL')
depends=('poppler')
makedepends=( git asciidoc )
provides=( pdfgrep )
backup=( )
source=( "git://gitorious.org/pdfgrep/pdfgrep.git" )
md5sums=( SKIP )
_gitname="pdfgrep"

pkgver() {
  cd "${srcdir}/${_gitname}"
  git describe --always | sed 's|-|.|g'
}

build() {
  cd "${srcdir}/${_gitname}"
  # set version
  # compile
  ./autogen.sh
  ./configure --prefix=/usr
  make
}

package() {
  cd "${srcdir}/${_gitname}"
  make prefix="$pkgdir/usr" install
}

