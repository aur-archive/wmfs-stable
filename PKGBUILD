# Maintainer: cron0 <jf.cron0@gmail.com>

pkgname=wmfs-stable
pkgver=201104
pkgrel=1
pkgdesc="A lightweight and highly configurable tiling window manager for X"
arch=('i686' 'x86_64')
url="http://www.wmfs.info/"
license=('BSD')
depends=('libxft' 'imlib2' 'libxinerama' 'libxrandr')
conflicts=('wmfs-git')
source=(http://wmfs.info/attachments/download/45/wmfs-$pkgver.tar.gz)
md5sums=('323fa55885d86783f104f936e6b12c75')

build() {
  cd "$srcdir/wmfs-$pkgver"

  ./configure --prefix /usr \
              --man-prefix /usr/share/man \
              --xdg-config-dir /etc/xdg
  make
}

package() {
  cd "$srcdir/wmfs-$pkgver"

  make DESTDIR=${pkgdir} install
  install -D -m644 COPYING ${pkgdir}/usr/share/licenses/wmfs/COPYING
}

