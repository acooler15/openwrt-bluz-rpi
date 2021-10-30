#
# Copyright (C) 2011-2020 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#
include $(TOPDIR)/rules.mk

PKG_NAME:=pi-bluetooth
PKG_RELEASE:=2

PKG_MAINTAINER:=acooler15 <acooler15@foxmail.com>
PKG_LICENSE:=GPL-2.0-only
PKG_LICENSE_FILES:=COPYING LICENSE

PKG_SOURCE_PROTO:=git
PKG_SOURCE_DATE:=2021-09-13
PKG_SOURCE_VERSION:=e1bb75aa83a632c86270e95f92826eb57ee09a77
PKG_SOURCE_URL:=https://github.com/RPi-Distro/pi-bluetooth.git
PKG_SOURCE:=$(PKG_NAME)-$(PKG_SOURCE_DATE).tar.gz
include $(INCLUDE_DIR)/package.mk



define Package/$(PKG_NAME)
  SECTION:=utils
  CATEGORY:=Utilities
  DEPENDS:=@TARGET_bcm27xx +bluez-daemon +bluez-firmware-rpidistro 
  TITLE:=Raspberry Pi bluetooth
  URL:=https://github.com/RPi-Distro/pi-bluetooth.git
endef

define Package/$(PKG_NAME)/description
  Raspberry Pi bluetooth.
  Loads BCM43xx firmware on boot
endef

define Build/Configure
true
endef

define Build/Compile
true
endef

define Package/$(PKG_NAME)/install
	$(INSTALL_DIR) $(1)/usr/bin/
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/usr/bin/btuart $(1)/usr/bin/btuart
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/usr/bin/bthelper $(1)/usr/bin/bthelper

	$(INSTALL_DIR) $(1)/etc/init.d
	$(INSTALL_BIN) ./files/pi-bluetooth.init $(1)/etc/init.d/pi-bluetooth
endef

$(eval $(call BuildPackage,pi-bluetooth))
