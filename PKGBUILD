
pkgname=nycmesh-gateway
pkgver=0.3.2068
pkgrel=1
pkgdesc="Configure system to act as a gateway to a cjdns based mesh network."
url="https://github.com/cjdelisle/${_pkgname}"
license=('GPL3')
arch=('i686' 'x86_64' 'armv6h' 'armv7h')
makedepends=('cjdns-git' 'radvd')
source=("git://github.com/cjdelisle/${_pkgname}.git#branch=master")
sha256sums=('SKIP')

package() {

    ## Add the cjdroute binary and systemd service file to the package
    install -D -m755 cjdroute "${pkgdir}"/usr/bin/cjdroute
    install -D -m644 contrib/systemd/${_pkgname}.service "${pkgdir}"/usr/lib/systemd/system/${_pkgname}.service
}

