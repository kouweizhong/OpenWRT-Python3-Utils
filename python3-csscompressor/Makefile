#
# Copyright (C) Daniel Kettle 2015
#
# CSS Compressor, licensed under BSD.
#


include $(TOPDIR)/rules.mk

PKG_NAME:=python3-csscompressor
PKG_VERSION:=0.9.3
PKG_RELEASE:=1
PKG_SOURCE:=csscompressor-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://pypi.python.org/packages/source/c/csscompressor/
PKG_MD5SUM:=8dcbdfd131def953dbf1e649eaa5db92

PKG_BUILD_DIR:=$(BUILD_DIR)/csscompressor-$(PKG_VERSION)

include $(INCLUDE_DIR)/package.mk
$(call include_mk, python3-package.mk)

define Package/python3-csscompressor
  SUBMENU:=Python3
  SECTION:=lang
  CATEGORY:=Languages
  TITLE:=CSS Compressor Library for Python
  DEPENDS:=+python3 +python3-pip
endef

define Package/python3-csscompressor/description
	Almost exact port of YUI CSS Compressor. Passes all original unittests.
	Tested under Python 2.6, 2.7 and 3.3
endef

define Host/Compile
	$(call Build/Compile/Py3Mod,,install --prefix=/usr --root=$(PKG_INSTALL_DIR))
endef

define Host/Install
	$(INSTALL_DIR) $(STAGING_DIR)$(PYTHON3_PKG_DIR)
	$(CP) \
		$(PKG_INSTALL_DIR)$(PYTHON3_PKG_DIR)/* \
		$(STAGING_DIR)$(PYTHON3_PKG_DIR)
endef

define Build/Compile
	$(call Build/Compile/Py3Mod,,install --prefix=/usr --root=$(PKG_INSTALL_DIR))
endef

define Package/python3-csscompressor/install
	$(INSTALL_DIR) $(1)$(PYTHON3_PKG_DIR)
	$(CP) \
		$(PKG_INSTALL_DIR)$(PYTHON3_PKG_DIR)/* \
		$(1)$(PYTHON3_PKG_DIR)/
	$(CP) $(PKG_INSTALL_DIR)/* $(1)/
endef

$(eval $(call HostBuild))
$(eval $(call BuildPackage,python3-csscompressor))
