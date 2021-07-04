#
# Copyright (C) 2018-2021 Ycarus (Yannick Chabanois) <ycarus@zugaina.org>
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=openmptcprouter-shrink
PKG_VERSION:=0.14
PKG_RELEASE:=1

include $(INCLUDE_DIR)/package.mk

MY_DEPENDS := \
    mptcp       \
    unbound-daemon unbound-control unbound-anchor \
    netifd      \
    luci-app-dsvpn \
    mc          \
    f2fs-tools \
    openmptcprouter \
    dnsmasq-full \
    uhttpd \
    uhttpd-mod-ubus \
    curl \
    iperf3-ssl luci-app-iperf \
    arptables \
    bind-dig \
    libnetfilter-conntrack ebtables ebtables-utils ip-full \
    iptables-mod-iface iptables-mod-ipmark iptables-mod-hashlimit iptables-mod-condition iptables-mod-trace iptables-mod-conntrack-extra iptables-mod-account \
    kmod-nf-nat kmod-nf-nathelper kmod-nf-nathelper-extra iptables-mod-extra \
    iptables-mod-ipsec kmod-crypto-authenc kmod-ipsec kmod-ipsec4 kmod-ipsec6 kmod-ipt-ipsec \
    wireless-tools \
    libiwinfo-lua \
    ca-bundle ca-certificates libustream-openssl \
    luci-mod-admin-full luci-app-firewall luci-app-glorytun-tcp luci-app-glorytun-udp luci-app-shadowsocks-libev luci-app-unbound luci-theme-openmptcprouter luci-base \
    luci-app-omr-tracker luci-app-omr-dscp \
    luci-app-sqm sqm-scripts-extra \
    luci-app-vnstat2 omr-quota luci-app-omr-quota \
    luci-app-mptcp luci-app-openmptcprouter luci-app-omr-bypass luci-app-mail luci-app-upnp \
    luci-app-opkg \
    luci-app-uhttpd \
    luci-mod-rpc rpcd-mod-rpcsys rpcd-mod-file rpcd-mod-iwinfo \
    luci-app-openvpn \
    macvlan \
    shadowsocks-libev-ss-server shadowsocks-libev-ss-tunnel \
    omr-6in4 ip6tables-mod-nat luci-proto-ipv6 6to4 6in4 6rd ip6tables \
    iftop \
    htop \
    tcpdump \
    ethtool \
    iputils-ping \
    !TARGET_mvebu:luci-proto-ppp \
    omr-update \
    rng-tools \
    openvpn-openssl \
    mmc-utils \
    kmod-random-core \
    ca-bundle openssl-util \
    dejavu-fonts-ttf-DejaVuSerif dejavu-fonts-ttf-DejaVuSerif-Bold dejavu-fonts-ttf-DejaVuSerif-Italic dejavu-fonts-ttf-DejaVuSerif-BoldItalic \
    iputils-tracepath netcat \
    luci-app-mlvpn mlvpn 464xlat  kmod-zram kmod-swconfig swconfig kmod-ipt-nat kmod-ipt-nat6 luci-app-https-dns-proxy kmod-tcp-nanqinlang iptables-mod-ipopt ss \
    luci-app-acl block-mount blockd fstools luci-app-shutdown libwebp luci-proto-gre

#OMR_SUPPORTED_LANGS := ar bg bn_BD ca en fi fr de el he hi hu it ja mr ms nb_NO pl pt_BR pt ro ru es sv uk vi zh_Hans zh_Hant
#OMR_SUPPORTED_LANGS := ar bg ca cs de en fi fr de el he hi hu it ja ko mr ms no oc pl pt-br pt ro ru es sk sv tr uk vi zh-cn zh-tw
OMR_SUPPORTED_LANGS := en

define Package/$(PKG_NAME)
SECTION:=OMR
CATEGORY:=OpenMPTCProuter
DEPENDS:=$(foreach p,$(MY_DEPENDS),+$(p)) $(foreach lang,$(OMR_SUPPORTED_LANGS),+LUCI_LANG_$(lang):luci-i18n-base-$(lang))
TITLE:=OpenMPTCProuter Full Package
endef

define Package/$(PKG_NAME)/description
OpenMPTCProuter Full package
endef

define Build/Compile
endef

define Package/$(PKG_NAME)/install
endef


$(eval $(call BuildPackage,$(PKG_NAME)))
