# Maintainer: Ainola

pkgname=gog_stardew_valley
pkgver=2.1.0.2
pkgrel=1
pkgdesc="A better Harvest Moon"
url="http://stardewvalley.net/"
license=('custom')
arch=('i686' 'x86_64')
depends=('sdl2' 'libcurl-gnutls')
source=("gog://gog_stardew_valley_${pkgver}.sh"
        "${pkgname}.desktop")
sha256sums=('18cef8174a21c556de17998bdb05827f55feca7b8e159106e22d970ce7dcc529'
            'd72c78a7b9f5977b0d4193518d51b336c853e8932b4e9d4a188b4fd3e7181465')

# You need to download the gog.com installer file manually or with lgogdownloader.
DLAGENTS+=("gog::/usr/bin/echo %u - This is is not a real URL, you need to download the GOG file manually to \"$PWD\" or setup a gog:// DLAGENT. Read this PKGBUILD for more information.")

# Prevent compressing final package
PKGEXT='.pkg.tar'



prepare(){
    cd "$srcdir/data/noarch"
    [ $CARCH == "x86" ]    && rm -r "$srcdir/data/noarch/game/mcs.bin.x86_64" && rm -r "$srcdir/data/noarch/game/StardewValley.bin.x86_64" &&  mv "$srcdir/data/noarch/game/mcs.bin.x86" "$srcdir/data/noarch/game/mcs"
    [ $CARCH == "x86_64" ] && rm -r "$srcdir/data/noarch/game/mcs.bin.x86" && rm -r "$srcdir/data/noarch/game/StardewValley.bin.x86" && mv "$srcdir/data/noarch/game/mcs.bin.x86_64" "$srcdir/data/noarch/game/mcs"
    # The launcher expects the user to be in the game dir
    echo -e "#!/bin/sh\ncd /opt/${pkgname}\n./start.sh" > "${srcdir}/${pkgname}"
}


package(){
    cd "$srcdir"
    # Install game
    install -d "${pkgdir}/opt/${pkgname}/"
    install -d "${pkgdir}/opt/${pkgname}/support"
    install -d "${pkgdir}/usr/bin/"
    cp -r "data/noarch/game/" "${pkgdir}/opt/${pkgname}/"
    install -Dm755 "data/noarch/start.sh" \
        "${pkgdir}/opt/${pkgname}/"
    install -Dm755 "data/noarch/start.sh" \
        "${pkgdir}/opt/${pkgname}/"
    install -Dm755 data/noarch/support/*.{sh,shlib} -t \
        "${pkgdir}/opt/${pkgname}/support"

    # Desktop integration
    install -Dm 644 "data/noarch/support/icon.png" \
        "${pkgdir}/usr/share/pixmaps/${pkgname}.png"
    install -Dm644 "data/noarch/docs/End User License Agreement.txt" \
        "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
    install -Dm 644 "${srcdir}/${pkgname}.desktop" \
        "${pkgdir}/usr/share/applications/${pkgname}.desktop"
    install -Dm 755 "${srcdir}/${pkgname}" "${pkgdir}/usr/bin/${pkgname}"
}
