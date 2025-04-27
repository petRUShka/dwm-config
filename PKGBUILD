# $Id: PKGBUILD 146423 2015-11-09 10:39:50Z spupykin $
# Maintainer: Sergej Pupykin <pupykin.s+arch@gmail.com>
# Contributor: Dag Odenhall <dag.odenhall@gmail.com>
# Contributor: Grigorios Bouzakis <grbzks@gmail.com>

pkgname=dwm
pkgver=6.5
pkgrel=1
pkgdesc="A dynamic window manager for X"
url="http://dwm.suckless.org"
arch=('i686' 'x86_64')
license=('MIT')
options=(zipman)
depends=(
  'libx11'
  'libxinerama'
  'libxft'
  'freetype2'
  'rofi'        # launcher bound to Alt+F2
  'alacritty'   # terminal bound to Alt+F1
)

optdepends=(
  'slock: screen-lock helper for Super+Shift+L (edit lockcmd if you use another locker)'
  'i3lock: alternative locker—change lockcmd in config.h if you prefer this'
)
install=dwm.install
source=(http://dl.suckless.org/dwm/dwm-$pkgver.tar.gz
	dwm.desktop)
md5sums=('446e84f5b151a1d4483fd72fd647e47e'
         '939f403a71b6e85261d09fc3412269ee')
_patches=(dwm-systray-20230922-9f88553.diff)

prepare() {
  cd $srcdir/$pkgname-$pkgver
  cp $startdir/config.h config.h
  make clean
  for PATCH in "${_patches[@]}"; do
    msg "${PATCH##*/}" && patch -Np1 -i "${startdir}/${PATCH##*/}"
  done
}

build() {
  cd $srcdir/$pkgname-$pkgver
  make X11INC=/usr/include/X11 X11LIB=/usr/lib/X11 FREETYPEINC=/usr/include/freetype2
}

package() {
  cd $srcdir/$pkgname-$pkgver
  make PREFIX=/usr DESTDIR=$pkgdir install
  install -m644 -D LICENSE $pkgdir/usr/share/licenses/$pkgname/LICENSE
  install -m644 -D README $pkgdir/usr/share/doc/$pkgname/README
  install -m644 -D $srcdir/dwm.desktop $pkgdir/usr/share/xsessions/dwm.desktop
}
