Cjdns builds for nycmesh.net nodes
==================================

This will hopefully become a collection of utilities to produce an image for a raspberry pi/beagle bone black/nanostation/etc that includes all the software necessary to start a node on the nycmesh network.

See [http://nycmesh.net/] for more information


Features
--------

* cjdns
    * systemd startup script to automatically generate cjdns config with ETHInterface
    * automatically generate .cjdadmin for web interface
* web interface to cjdns configuration (another package?)
* gateway from local network to cjdns network [https://github.com/cjdelisle/cjdns/blob/master/doc/nat-gateway.md]
    * ip6tables configuration
        * ipv6-forwarding.conf -> /etc/sysctl.d/ipv6-forwarding.conf
        * ip6tables.rules -> /etc/iptables/ip6tables.rules
        * systemctl enable ip6tables
        * systemctl start ip6tables
    * radvd to broadcast route
        * radvd.conf -> /etc/radvd.conf
        * systemctl enable radvd
        * systemctl start radvd
    * configure static ip on eth0
        * eth0-ipv6static -> /etc/netctl/
        * systemctl stop netctl@eth0
        * systemctl disable netctl@eth0
        * systemctl start netctl@eth0-ipv6static
        * systemctl enable netctl@eth0-ipv6static

* DNS?

