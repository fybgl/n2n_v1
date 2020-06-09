#
# Copyright (C) 2008 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
include $(TOPDIR)/rules.mk

PKG_NAME:=n2n
PKG_VERSION:=v1.3.2
PKG_REV:=171cd793421776d52224b75f28639e3aca743c29
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.bz2
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)
PKG_SOURCE_URL:=https://github.com/fybgl/n2n_v1.git
PKG_SOURCE_PROTO:=git
PKG_SOURCE_VERSION:=$(PKG_REV)

include $(INCLUDE_DIR)/package.mk

define Package/n2n
  SECTION:=net
  CATEGORY:=Network
  TITLE:=VPN tunneling daemon
  URL:=http://www.ntop.org/n2n/
  SUBMENU:=VPN
  DEPENDS:=libpthread
endef


define Build/Configure
endef

define Build/Compile
	$(MAKE) CC="$(TARGET_CC)" -C $(PKG_BUILD_DIR)
endef


define Package/n2n/install
	$(INSTALL_DIR) $(1)/usr/sbin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/edge $(1)/usr/sbin/
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/supernode $(1)/usr/sbin/
endef

$(eval $(call BuildPackage,n2n))
