# Copyright (C) 2019 Openwrt.org
#
# This is a free software, use it under Apache Licene 2.0 & GNU General Public License v3.0.
#

include $(TOPDIR)/rules.mk

LUCI_TITLE:=luci for haproxy and shadowsocks
LUCI_DEPENDS:=+haproxy
LUCI_PKGARCH:=all
PKG_NAME:=luci-app-haproxy-tcp
PKG_VERSION=1.5
PKG_RELEASE:=1
PKG_MAINTAINER:=Alex Zhuo <1886090@gmail.com>

include $(TOPDIR)/feeds/luci/luci.mk

include $(INCLUDE_DIR)/package.mk

define Package/$(PKG_NAME)
	SECTION:=luci
	CATEGORY:=LuCI
	SUBMENU:=3. Applications
	TITLE:=luci for haproxy and shadowsocks
	PKGARCH:=all
	DEPENDS:=+haproxy
endef

define Package/$(PKG_NAME)/description
    A luci app for haproxy with shadowsocks
endef

define Package/$(PKG_NAME)/postinst
#!/bin/sh
rm -rf /tmp/luci*
echo stopping haproxy
/etc/init.d/haproxy stop
/etc/init.d/haproxy disable
echo haproxy disabled
exit 0
endef

# call BuildPackage - OpenWrt buildroot signature
