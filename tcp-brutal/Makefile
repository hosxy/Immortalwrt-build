include $(TOPDIR)/rules.mk
include $(INCLUDE_DIR)/kernel.mk

PKG_NAME:=tcp-brutal
PKG_VERSION:=2.0.1
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://codeload.github.com/HyNetworks/tcp-brutal/tar.gz/v$(PKG_VERSION)?
PKG_HASH:=55889848e85463a4547c2691e6cf7bd1b140305b808aa4004b8c2a19d1f44efd
PKG_LICENSE:=GPL-3.0

PKG_MAINTAINER:=hosxy <hosxy@live.com>

include $(INCLUDE_DIR)/package.mk

define KernelPackage/brutal
	SECTION:=kernel
	SUBMENU:=Network Support
	TITLE:=TCP Brutal Kernel module
	FILES:=$(PKG_BUILD_DIR)/brutal.$(LINUX_KMOD_SUFFIX)
	AUTOLOAD:=$(call AutoLoad,30,brutal)
endef

define KernelPackage/brutal/description
	Hysteria's congestion control algorithm ported to kernel mode TCP
endef

include $(INCLUDE_DIR)/kernel-defaults.mk

define Build/Configure
endef

define Build/Compile
	$(KERNEL_MAKE) M="$(PKG_BUILD_DIR)" modules
endef

$(eval $(call KernelPackage,brutal))
