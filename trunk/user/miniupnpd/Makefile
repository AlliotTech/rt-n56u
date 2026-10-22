SRC_NAME=miniupnpd-2.3.11

# reference to iptables package
IPT_VERSION:=iptables-1.4.16.3

# disable support IPv6 yet, because no profit w/o IGDv2
# e.g. Windows not supported IGDv2 and UPnP not worked
ENABLE_IPV6:=0

IPTABLESPATH=$(ROOTDIR)/user/iptables/$(IPT_VERSION)

all:
	cd $(SRC_NAME) && PKG_CONFIG= ./configure --firewall=iptables --iptablespath=$(IPTABLESPATH)
	$(MAKE) -f Makefile.linux -C $(SRC_NAME)

clean:
	$(MAKE) -f Makefile.linux -C $(SRC_NAME) clean
	rm -f miniupnpd

romfs:
	cp $(SRC_NAME)/miniupnpd .
	$(ROMFSINST) /usr/bin/miniupnpd

