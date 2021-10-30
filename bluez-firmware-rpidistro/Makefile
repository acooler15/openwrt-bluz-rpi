#
# Copyright (C) 2011-2020 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#
include $(TOPDIR)/rules.mk

PKG_NAME:=bluez-firmware-rpidistro
PKG_RELEASE:=1

PKG_MAINTAINER:=acooler15 <acooler15@foxmail.com>
PKG_LICENSE:=GPL-2.0-only
PKG_LICENSE_FILES:=COPYING LICENSE

PKG_SOURCE_PROTO:=git
PKG_SOURCE_DATE:=2021-01-28
PKG_SOURCE_VERSION:=e7fd166981ab4bb9a36c2d1500205a078a35714d
PKG_SOURCE_URL:=https://github.com/RPi-Distro/bluez-firmware.git
PKG_MIRROR_HASH:=6089956341235ce45da1aca495810b5616a328177f5b1b021652e49a3366140b
PKG_SOURCE:=$(PKG_NAME)-$(PKG_SOURCE_DATE).tar.gz
include $(INCLUDE_DIR)/package.mk



define Package/$(PKG_NAME)
  SECTION:=utils
  CATEGORY:=Utilities
  DEPENDS:=@TARGET_bcm27xx
  TITLE:=Bluetooth firmware files for RaspberryPi hardware
  URL:=https://github.com/RPi-Distro/bluez-firmware.git
endef

define Package/$(PKG_NAME)/description
  Bluetooth firmware files for RaspberryPi hardware
endef


define Build/Configure
true
endef

define Build/Compile
true
endef

define Package/$(PKG_NAME)/install
	$(INSTALL_DIR) $(1)/lib/firmware/brcm
	$(CP) $(PKG_BUILD_DIR)/broadcom/*.hcd $(1)/lib/firmware/brcm/
endef

$(eval $(call BuildPackage,bluez-firmware-rpidistro))
