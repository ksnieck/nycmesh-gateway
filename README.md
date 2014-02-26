Cjdns builds for nycmesh.net nodes
==================================

This will hopefully become a collection of utilities to produce an image for a raspberry pi/beagle bone black/nanostation/etc that includes all the software necessary to start a node on the nycmesh network.

See [http://nycmesh.net/] for more information


Features
--------

* cjdns (duh)
* automatically generate cjdns config with ETHInterface
* start cjdns at boot
* web interface to cjdns configuration
* gateway from local network to cjdns network
  * dhcp server to give out ipv6 addr
  * NAT to tun0



