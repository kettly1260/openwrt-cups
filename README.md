
download https://downloads.openwrt.org/releases/19.07.3/targets/ramips/mt7621/openwrt-sdk-19.07.3-ramips-mt7621_gcc-7.5.0_musl.Linux-x86_64.tar.xz

tar vxJf sdk.tar.xz

cd openwrt-sdk

echo "src-git cups https://github.com/fengchen-github/openwrt-cups.git" >> feeds.conf.default

./scripts/feeds update -a

./scripts/feeds install -a

make packages/cups/compile V=s

copy bin/packages/<arch>/cups/*.ipk to router
