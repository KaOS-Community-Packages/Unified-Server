pkgname=unified-server
_pkgname=urserver
pkgver=3.3.4.734
pkgrel=1
pkgdesc='The one-and-only remote for your computer.'
arch=('x86_64')
url="https://www.unifiedremote.com"
license=('custom: UNIFIED INTENTS')
options=('!strip')
depends=("libx11" "libxext")
optdepends=("libstdc++5")
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
	cp "${pkgdir}"/opt/urserver/urserver-autostart.desktop ~/.config/autostart/urserver-autostart.desktop
}
