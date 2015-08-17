# Maintainer: John Lenz <lenz@math.uic.edu>

pkgname=rtl8812au-dkms
pkgver=4.2.2.7502.20130517
pkgrel=1
pkgdesc='rtl8812au linux kernel driver for Realtek AC1200 (802.11ac) Wireless Dual-Band USB Adapter'
arch=('i686' 'x86_64')
license=('GPL2')
depends=('dkms' 'linux-headers')
install=${pkgname}.install
url='https://github.com/wuzzeb/rtl8812AU_8821AU_linux'
options=(!strip)
source=('git+https://github.com/wuzzeb/rtl8812AU_8821AU_linux.git' 'dkms.conf' 'makefile.patch')
md5sums=('SKIP' '6583f291bf6310835a985354fa6261d4' 'ea35eb0a86680c0a8de60e0e48881e48')

build() {
	cd ${srcdir}/rtl8812AU_8821AU_linux
	patch -p0 < ../makefile.patch
}

package() {
	install -dm 755 "${pkgdir}/usr/src"
	cp -dr --no-preserve=ownership "${srcdir}/rtl8812AU_8821AU_linux" "${pkgdir}/usr/src/rtl8812au-${pkgver}"
	install -D -m 644 dkms.conf "${pkgdir}/usr/src/rtl8812au-${pkgver}"
}
