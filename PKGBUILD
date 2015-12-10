pkgname=unified-remote-server
_pkgname=urserver
pkgver=3.3.4.734
pkgrel=1
pkgdesc='Unified Remote Server for Linux. Easily the best way of controlling your PC from your smartphone.
  * Easily connect using WiFi (and Bluetooth coming soon).
  * Automatic server detection to easily find servers installed on your network.
  * Server password protection and encryption for added security.
  * Web-based server manager lets you configure your server from anywhere.
  * Basic Input remote to control mouse movement and keyboard input.
  * Loaded with remotes to control many media applications, tools, system settings, etc.
  * App available for Android, iOS, and Windows Phone.'
arch=('x86_64')
url="https://www.unifiedremote.com"
license=('Unified Intents AB')
options=('!strip')
depends=("libx11" "libxext" "libstdc++5")
source=("https://www.unifiedremote.com/static/builds/server/linux-x64/734/${_pkgname}-${pkgver}.deb")
md5sums=('f8bf2ece6c2d2cf8c3968afe620bfb67')

package() {
  cd "${srcdir}"

	tar -xzf data.tar.gz -C "${pkgdir}"

	install -d "${pkgdir}"/usr/share/applications
	install -d "${pkgdir}"/usr/share/pixmaps
	install -d "${pkgdir}"/usr/share/icons
	# opt Source
	install -d "${pkgdir}"/opt/urserver
}
