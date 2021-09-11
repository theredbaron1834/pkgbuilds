# Maintainer: #####

pkgbase=rbutil-git
pkgname=('rbutil-git' 'rbspeex-git')
pkgver=1.4.0.r1593.9f6ce046cb
pkgrel=1
arch=('x86_64')
url='http://www.rockbox.org/twiki/bin/view/Main/RockboxUtility'
license=('GPL')
makedepends=('crypto++' 'git' 'libusb' 'qt5-base' 'qt5-tools' 'speex' 'speexdsp')
source=('rockbox::git://git.rockbox.org/rockbox')
sha256sums=('SKIP')

pkgver() {
  cd "$srcdir/rockbox/rbutil"

  _tag='rbutil_1.4.0'

  printf "%s.r%s.%s" "${_tag#rbutil_}" "$(git rev-list --count ${_tag}..HEAD)" "$(git rev-parse --short HEAD)"
}

build() {

  cd "$srcdir/rockbox/rbutil/rbutilqt"

  qmake
  make

  cd ../../tools/rbspeex

  make
  echo  "[Desktop Entry]
Exec=/usr/bin/bijint-tokei
Name=Tokei
OnlyShowIn=LXQt;
Type=Application
Version=1.0
X-LXQt-Need-Tray=true
" > "$srcdir/rbutil.desktop"
}

package_rbutil-git(){
  pkgdesc='Rockbox Utility'
  depends=('gcc-libs' 'glibc' 'qt5-base' 'speex' 'speexdsp' 'zlib'
           'libusb-1.0.so')
  optdepends=('espeak: TTS engine'
              'festival: TTS engine'
              'flite: TTS engine'
              'rbspeex-git: Generate voice/talk files from external sources')
  provides=('rbutil')
  conflicts=('rbutil')

  cd rockbox/rbutil/rbutilqt
  install -dm 755 "${pkgdir}"/usr/{bin,share/{applications,pixmaps}}
  install -m 755 RockboxUtility "${pkgdir}"/usr/bin/
  install -m 644 icons/rockbox.ico "${pkgdir}"/usr/share/pixmaps/rbutil.png
    install -m 644 "$srcdir/rbutil.desktop" "${pkgdir}"/usr/share/applications/
}

package_rbspeex-git(){
  pkgdesc='Rockbox Speex Codec'
  depends=('glibc' 'speex' 'speexdsp')
  provides=('rbspeex')
  conflicts=('rbspeex')

  cd rbutil/tools

  install -dm 755 "${pkgdir}"/usr/bin
  install -m 755 rbspeex{dec,enc} "${pkgdir}"/usr/bin/
}

# vim: ts=2 sw=2 et:
