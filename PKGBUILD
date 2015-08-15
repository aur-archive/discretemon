# Maintainer: Gen2ly <toddrpartridge@gmail.com>

pkgname=discretemon
pkgver=1.7
pkgrel=2
pkgdesc="Sets an external monitor with a laptop as discrete (xorg)"
arch=('any')
url="https://github.com/Gen2ly/discretemon"
license=('GPL')
groups=()
depends=('bc' 'systemd' 'xorg-xdpyinfo' 'xuserrun')
install=${pkgname}.install
source=(89-${pkgname}.rules
        ${pkgname}
        ${pkgname}-resume.service
        ${pkgname}.desktop)
md5sums=('ec41d76cc806c22dd31b79689aa31c33'
         '6437fc37a9f946ef642c73114442ed05'
         '2534d9bd93595ecb66c0f8a1f410e770'
         '31528093e9098c4b90981aed017fbe57')

package() {

 install -Dm644 89-${pkgname}.rules $pkgdir/etc/udev/rules.d/89-${pkgname}.rules
 install -Dm755 ${pkgname}          $pkgdir/usr/bin/${pkgname}
 install -Dm644 ${pkgname}-resume.service \
   $pkgdir/etc/systemd/system/${pkgname}-resume.service
 install -d                         $pkgdir/etc/gdm/Init
 ln -s /usr/bin/discretemon         $pkgdir/etc/gdm/Init/${pkgname}
 install -Dm644 ${pkgname}.desktop  $pkgdir/etc/xdg/autostart/${pkgname}.desktop

}
# vim:set ts=2 sw=2 et:
