# Maintainer: Brian Bidulock <bidulock@openss7.org>
pkgname=wmclock
pkgver=1.0.15
pkgrel=1
pkgdesc="Dockable clock applet for Window Maker"
arch=('i686' 'x86_64')
url="http://www.bluestop.org/wmclock/"
license="GPL"
depends=('libxpm')
optdepends=('windowmaker')
makedepends=('')
source=("${pkgname}-${pkgver}.tar.gz::http://windowmaker.org/dockapps/?download=wmclock-1.0.15.tar.gz")
md5sums=('6b8a9324149dc770804d0ef6114616a0')

prepare() {
  cd "${srcdir}/dockapps-"*

  #for patch in "${srcdir}/"*.patch ; do
  #  patch -Np1 -i "${patch}"
  #done
}

build() {
  cd "${srcdir}/dockapps-"*

  autoreconf -i
  ./configure --prefix=/usr \
      --mandir=/usr/share/man \
      --with-lang=english
  make
}

package() {
  cd "${srcdir}/dockapps-"*
  make DESTDIR=${pkgdir} install
  install -Dm644 README ${pkgdir}/usr/share/doc/wmclock/README
}

