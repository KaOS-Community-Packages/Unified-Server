pkgname=unified-remote-server
_pkgname=urserver
pkgver=3.3.5.738
pkgrel=1
pkgdesc='Unified Remote Server for Linux. Easily the best way of controlling your PC from your smartphone.'
arch=('x86_64')
url="https://www.unifiedremote.com"
license=('Unified Intents AB')
install=$pkgname.install
depends=("libx11" "libxext" "libstdc++5")
optdepends=('bluez' 'bluez-libs: To Enable the Bluetooth Protocol')
source=("https://www.unifiedremote.com/static/builds/server/linux-x64/${pkgver/*./}/${_pkgname}-${pkgver}.deb")
md5sums=('c6bc60afaba0b24e86135e4f9a7e4733')

package() {
  cd "${srcdir}"

	tar -xzf data.tar.gz

	#fix desktop file
	sed -i -e '9,24d;26d' $(find . -name 'urserver.desktop')

        # opt,usr Sources
	install -d "${pkgdir}"/opt/urserver
        cp -r {opt,usr} "${pkgdir}/"
        
        # clean up permissions
	find "${pkgdir}" -type d | xargs -I {} chmod -R 755 "{}"
	find "${pkgdir}" -type f | xargs -I {} chmod -R 644 "{}"
	chmod 755 "${pkgdir}/opt/urserver/urserver"
	chmod 755 "${pkgdir}/opt/urserver/urserver-start"
	chmod 755 "${pkgdir}/opt/urserver/urserver-stop"
}
