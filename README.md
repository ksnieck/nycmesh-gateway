# Cjdns builds for nycmesh.net nodes

This will hopefully become a collection of utilities to produce an image for a raspberry pi/beagle bone black/nanostation/etc that includes all the software necessary to start a node on the nycmesh network.

See http://nycmesh.net/ for more information about the larger meshlocal project

## Features
* cjdns
    * systemd startup script to automatically generate cjdns config with ETHInterface
    * automatically generate .cjdadmin for web interface
* web interface to cjdns configuration (nodejs in contrib?)
* gateway from local network to cjdns network (https://github.com/cjdelisle/cjdns/blob/master/doc/nat-gateway.md)
    * ip6tables configuration
    * radvd to broadcast route
    * configure static ipv6 on eth0
* DNS

## Setup
The idea is to have an image setup that does this for you, but until then:
+ Put archlinuxarm on your raspberry pi: http://archlinuxarm.org/platforms/armv6/raspberry-pi
+ Get this repository:

    git clone http://github.com/ksnieck/nycmesh-gateway/

+ build the gateway configuration package

    cd nycmesh-gateway/cjdns-gateway
    makepkg

+ you probably will have to visit http://aur.archlinux.org and install dependencies and try again
+ edit /etc/cjdroute.conf and uncomment ETHInterface
+ restart cjdns

    sudo systemctl restart cjdns

ask in irc.eftnet.org #nycmeshnet for help: [web chat](http://client03.chat.mibbit.com/?channel=%23nycmeshnet&server=irc.umich.edu)

