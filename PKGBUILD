# Maintainer: Michaël Serpieri <mickybart@pygoscelis.org>

pkgname=hybris-usb
pkgver=0.1
pkgrel=2
pkgdesc="USB control for Android with hybris"
arch=('armv7h')
url=""
license=('custom')
provides=()
depends=('systemd' 'dhcp' 'net-tools')
options=()
source=('usb-tethering'
	'usb-tethering.service'
	'dhcpd.conf'
	'tmpfiles.d.hybris-usb.conf')
md5sums=('2d270508c91e94997236e5dacd7bbc8d'
         '7976b6c3d662802cc54e3458ec3b891e'
         '8d25b1c3f1146635800db77f300b908c'
         '91422a3f2a69c9800d25cd65358fe5df')

package() {


  # usb tethering

  mkdir -p ${pkgdir}/usr/bin
  install -m755 "$srcdir"/usb-tethering "$pkgdir"/usr/bin/

  mkdir -p ${pkgdir}/usr/lib/systemd/system/
  install -m644 "$srcdir"/usb-tethering.service "$pkgdir"/usr/lib/systemd/system/

  # dhcpd configuration

  mkdir -p ${pkgdir}/usr/lib/tmpfiles.d/
  install -m644 "$srcdir"/tmpfiles.d.hybris-usb.conf "$pkgdir"/usr/lib/tmpfiles.d/hybris-usb.conf

  mkdir -p ${pkgdir}/etc/hybris-usb/
  install -m644 "$srcdir"/dhcpd.conf "$pkgdir"/etc/hybris-usb/
}

