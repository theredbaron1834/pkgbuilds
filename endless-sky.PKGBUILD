# Maintainer: Stephen Bell <theredbaron1834 @ yahoo.com>

pkgname=endless-sky-git
pkgver=20151021.a1ed871
pkgrel=1
pkgdesc='A galaxy lies open for you to explore. Endless Sky is a 2D space trading and combat game similar to the classic Escape Velocity series. Explore other star systems.'
url='https://endless-sky.github.io/'
arch=('i686' 'x86_64')
license=('GPL V2')
makedepends=('git')
source=("endless-sky::git+https://github.com/endless-sky/endless-sky.git")
sha1sums=('SKIP')
depends=('scons' 'sdl2' 'libpng12' 'libjpeg-turbo' 'glew' 'openal')

pkgver() {
	cd "${srcdir}/endless-sky"
	git log -1 --format='%cd.%h' --date=short | tr -d -
}

build() {
	cd "${srcdir}/endless-sky"
	scons
}

package() {
  cd "$pkgdir"
  install -m777 -d "$pkgdir/opt/endless-sky"

  cp -r "$srcdir/endless-sky/data/" "$pkgdir/opt/endless-sky/"
  cp -r "$srcdir/endless-sky/images/" "$pkgdir/opt/endless-sky"
  cp -r "$srcdir/endless-sky/sounds/" "$pkgdir/opt/endless-sky"
  cp "$srcdir/endless-sky/endless-sky" "$pkgdir/opt/endless-sky"
  cp "$srcdir/endless-sky/README.md" "$pkgdir/opt/endless-sky"
  cp "$srcdir/endless-sky/license.txt" "$pkgdir/opt/endless-sky"
  cp "$srcdir/endless-sky/credits.txt" "$pkgdir/opt/endless-sky"
  cp "$srcdir/endless-sky/endless-sky.iconset/icon_256x256.png" "$pkgdir/opt/endless-sky/icon.png"
  mkdir -p "$pkgdir/usr/share/applications/"
  mkdir -p "$pkgdir/usr/bin/"
  echo "[Desktop Entry]
Name=Endless-Sky
GenericName=Endless Sky
Comment=Space exploration, trading, and combat game.
Exec=endless-sky
Icon=/opt/endless-sky/icon.png
Terminal=false
Type=Application
Categories=Game;" > "$pkgdir/usr/share/applications/endless-sky.desktop"
  echo "#!/bin/sh
cd /opt/endless-sky/
./endless-sky" > "$pkgdir/usr/bin/endless-sky"
  chmod +x "$pkgdir/usr/bin/endless-sky"
}
