
pkgname=nycmesh-gateway
pkgver=0.3.2068
pkgrel=1
pkgdesc="Configure system to act as a gateway to a cjdns based mesh network."
url="https://github.com/cjdelisle/${_pkgname}"
license=('GPL3')
arch=('i686' 'x86_64' 'armv6h' 'armv7h')
makedepends=('cjdns-git' 'radvd' 'netctl')
source=("git://github.com/cjdelisle/${_pkgname}.git#branch=master")
sha256sums=('SKIP')
install="services.install"

package() {
    # install config files
    install -D -m644 ip6tables.rules "${pkgdir}"/etc/iptables/ip6tables.rules
    install -D -m644 ipv6-forwarding.conf "${pkgdir}"/etc/sysctl.d/ipv6-forwarding.conf
    install -D -m644 radvd.conf "${pkgdir}"/etc/radvd.conf
    install -D -m644 ip6tables.rules "${pkgdir}"/etc/iptables/ip6tables.rules
    install -D -m644 eth0_ipv6static "${pkgdir}"/etc/netctl/eth0_ipv6static
}


