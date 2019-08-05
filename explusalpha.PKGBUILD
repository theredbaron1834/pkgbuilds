# Maintainer: Stephen Bell <theredbaron1834 @ yahoo.com>
pkgname=explusalpha
pkgrel=1
pkgver=1.5.14
pkgdesc="A collection of Emus."
arch=('x86_64')
url="http://www.explusalpha.com"
license=('GPLv3')
depends=('gtk3')
makedepends=('tar')

build() {

    msg "Grabbing emu...."
#  curl 'http://www.explusalpha.com/home/general-info/platforms/linux/explusalpha.com%20Emu%20Bundle%201.5.14.tar.xz?attredirects=0'  -L -o emu.tar.xz
    tar xf emu.tar.xz
    msg "Grabbing icons...."
    install -m777 -d icons
#    curl 'https://upload.wikimedia.org/wikipedia/commons/9/95/MSX-Logo.svg' -L -o icons/MSX.svg
#    curl 'https://upload.wikimedia.org/wikipedia/en/f/f3/Neo_Geo_logo.svg' -L -o icons/Neo.svg
#    curl 'https://upload.wikimedia.org/wikipedia/en/0/08/Atari_2600_logo.svg' -L -o icons/Atari.svg
#    curl 'https://upload.wikimedia.org/wikipedia/commons/8/8a/Gameboy_advance_logo.svg' -L -o icons/GBA.svg
#    curl 'https://upload.wikimedia.org/wikipedia/commons/9/90/Game_Boy_Color_Logo.svg' -L -o icons/GBC.svg
#    curl 'https://upload.wikimedia.org/wikipedia/commons/7/74/Sega_genesis_logo.svg' -L -o icons/Genesis.svg
#    curl 'https://upload.wikimedia.org/wikipedia/commons/0/0d/NES_logo.svg' -L -o icons/NES.svg
#    curl 'https://upload.wikimedia.org/wikipedia/commons/thumb/7/71/SNK_NeoGeo_Pocket_logo.png/461px-SNK_NeoGeo_Pocket_logo.png' -L -o icons/NGP.png
#    curl 'https://upload.wikimedia.org/wikipedia/en/4/4e/PC_Engine_logo.png' -L -o icons/PCE.svg
#    curl 'https://upload.wikimedia.org/wikipedia/en/4/42/SegaSaturn.png' -L -o icons/Saturn.svg
#    curl 'https://upload.wikimedia.org/wikipedia/commons/3/33/Super_Nintendo_Entertainment_System_logo.svg' -L -o icons/SNES.svg
}

package() {
    cd "$pkgdir"
    install -m777 -d "$pkgdir/opt/ExplusalphaEmu"
    install -m777 -d "$pkgdir/opt/ExplusalphaEmu/SNES9x.emu"
    install -m755 -d "$pkgdir/usr/share/applications/"
    cp -r $srcdir/'explusalpha.com Emu Bundle 1.5.14'/2600.emu "$pkgdir/opt/ExplusalphaEmu"

    cp -r $srcdir/'explusalpha.com Emu Bundle 1.5.14'/GBA.emu "$pkgdir/opt/ExplusalphaEmu"
    cp -r $srcdir/'explusalpha.com Emu Bundle 1.5.14'/GBC.emu "$pkgdir/opt/ExplusalphaEmu"
    cp -r $srcdir/'explusalpha.com Emu Bundle 1.5.14'/MD.emu "$pkgdir/opt/ExplusalphaEmu"
    cp -r $srcdir/'explusalpha.com Emu Bundle 1.5.14'/MSX.emu "$pkgdir/opt/ExplusalphaEmu"
    cp -r $srcdir/'explusalpha.com Emu Bundle 1.5.14'/NEO.emu "$pkgdir/opt/ExplusalphaEmu"
    cp -r $srcdir/'explusalpha.com Emu Bundle 1.5.14'/NES.emu "$pkgdir/opt/ExplusalphaEmu"
    cp -r $srcdir/'explusalpha.com Emu Bundle 1.5.14'/NGP.emu "$pkgdir/opt/ExplusalphaEmu"
    cp -r $srcdir/'explusalpha.com Emu Bundle 1.5.14'/PCE.emu "$pkgdir/opt/ExplusalphaEmu"
    cp $srcdir/'explusalpha.com Emu Bundle 1.5.14'/'Snes9x EX+'/* "$pkgdir/opt/ExplusalphaEmu/SNES9x.emu"

    cp -r "$srcdir/icons" "$pkgdir/opt/ExplusalphaEmu/icons"

  echo "[Desktop Entry]
Name=2600.emu
GenericName=2600.emu
Comment=A feature full 2600 emulator.
Exec=/opt/ExplusalphaEmu/2600.emu/2600emu
Icon=/opt/ExplusalphaEmu/icons/Atari.svg
Terminal=false
Type=Application
Categories=Game;" > "$pkgdir/usr/share/applications/Explusalpha2600.desktop"

  echo "[Desktop Entry]
Name=GBA.emu
GenericName=GBA.emu
Comment=A feature full GBA emulator.
Exec=/opt/ExplusalphaEmu/GBA.emu/gbaemu
Icon=/opt/ExplusalphaEmu/icons/GBA.svg
Terminal=false
Type=Application
Categories=Game;" > "$pkgdir/usr/share/applications/ExplusalphaGBA.desktop"

  echo "[Desktop Entry]
Name=GBC.emu
GenericName=GBC.emu
Comment=A feature full GBC emulator.
Exec=/opt/ExplusalphaEmu/GBC.emu/gbcemu
Icon=/opt/ExplusalphaEmu/icons/GBC.svg
Terminal=false
Type=Application
Categories=Game;" > "$pkgdir/usr/share/applications/ExplusalphaGBC.desktop"

  echo "[Desktop Entry]
Name=MegaDrive.emu
GenericName=MegaDrive.emu
Comment=A feature full MegaDrive/Genesis emulator.
Exec=/opt/ExplusalphaEmu/MD.emu/mdemu
Icon=/opt/ExplusalphaEmu/icons/Genesis.svg
Terminal=false
Type=Application
Categories=Game;" > "$pkgdir/usr/share/applications/ExplusalphaMD.desktop"

  echo "[Desktop Entry]
Name=MSX.emu
GenericName=MSX.emu
Comment=A feature full MSX emulator.
Exec=/opt/ExplusalphaEmu/MSX.emu/msxemu
Icon=/opt/ExplusalphaEmu/icons/MSX.svg
Terminal=false
Type=Application
Categories=Game;" > "$pkgdir/usr/share/applications/ExplusalphaMSX.desktop"

  echo "[Desktop Entry]
Name=Neo.emu
GenericName=Neo.emu
Comment=A feature full NeoGeo emulator.
Exec=/opt/ExplusalphaEmu/NEO.emu/neoemu
Icon=/opt/ExplusalphaEmu/icons/Neo.svg
Terminal=false
Type=Application
Categories=Game;" > "$pkgdir/usr/share/applications/ExplusalphaNeo.desktop"

  echo "[Desktop Entry]
Name=NES.emu
GenericName=NES.emu
Comment=A feature full Nes emulator.
Exec=/opt/ExplusalphaEmu/NES.emu/nesemu
Icon=/opt/ExplusalphaEmu/icons/NES.svg
Terminal=false
Type=Application
Categories=Game;" > "$pkgdir/usr/share/applications/ExplusalphaNES.desktop"

  echo "[Desktop Entry]
Name=NGP.emu
GenericName=NGP.emu
Comment=A feature full NeoGeo Pocket Color emulator.
Exec=/opt/ExplusalphaEmu/NGP.emu/ngpemu
Icon=/opt/ExplusalphaEmu/icons/NGP.png
Terminal=false
Type=Application
Categories=Game;" > "$pkgdir/usr/share/applications/ExplusalphaNGP.desktop"

  echo "[Desktop Entry]
Name=PCEngine.emu
GenericName=PCEngine.emu
Comment=A feature full PC Engine/Turbografx16 emulator.
Exec=/opt/ExplusalphaEmu/PCE.emu/pceemu
Icon=/opt/ExplusalphaEmu/icons/PCE.svg
Terminal=false
Type=Application
Categories=Game;" > "$pkgdir/usr/share/applications/ExplusalphaPCE.desktop"

  echo "[Desktop Entry]
Name=SNES.emu
GenericName=SNES.emu
Comment=A feature full Super Nintendo emulator.
Exec=/opt/ExplusalphaEmu/SNES9x.emu/s9xp
Icon=/opt/ExplusalphaEmu/icons/SNES.svg
Terminal=false
Type=Application
Categories=Game;" > "$pkgdir/usr/share/applications/ExplusalphaSNES9x.desktop"

}
