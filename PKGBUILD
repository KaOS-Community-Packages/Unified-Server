pkgname=urserver
pkgver=3.4.0.740
pkgrel=2
pkgdesc='Unified Remote Server for Linux. Easily the best way of controlling your PC from your smartphone.'
arch=('x86_64')
url="https://www.unifiedremote.com"
license=('Unified Intents AB')
conflicts=('unified-remote-server')
install=$pkgname.install
depends=("libx11" "libxext")
optdepends=('bluez' 'bluez-libs: To Enable the Bluetooth Protocol')
source=("https://www.unifiedremote.com/static/builds/server/linux-x64/${pkgver/*./}/${pkgname}-${pkgver}.deb")
md5sums=('178a2511d25b06d061c1a61f7f98db07')

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
