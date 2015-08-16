# $Id: PKGBUILD 161866 2012-06-16 00:18:39Z ibiru $
# Maintainer : Ionut Biru <ibiru@archlinux.org>

pkgname=libva-g45-h264
pkgver=20120619
pkgrel=3
pkgdesc="Video Acceleration (VA) API for Intel G45 chipsets with H264 support on Linux"
arch=('i686' 'x86_64')
url="http://freedesktop.org/wiki/Software/vaapi"
license=('MIT')
depends=( 'libgl' 'libdrm' 'libxfixes')
makedepends=('mesa' 'git')
options=('!libtool')
install=libva.install
conflicts=('libva')
provides=('libva')
replaces=('libva')

build() {
cd "$srcdir"
  git clone git://anongit.freedesktop.org/vaapi/libva -b g45-h264 libva-g45-h264
  
  cd "$pkgname"
  ./autogen.sh
  ./configure --prefix=/usr
  make
}

package() {
  cd "$pkgname"
  make DESTDIR="$pkgdir" install
  install -m644 -D COPYING "$pkgdir/usr/share/licenses/$pkgname/COPYING"
}

# vim:set ts=2 sw=2 et:
sha256sums=('1b55307d9e82ce403ba5103e994e71029aecb65b1722932431754008ce50bfb4')
