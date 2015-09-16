# OpenWrt-patches

##Download source

###For Chaos Calmer 15.05
git clone git://git.openwrt.org/15.05/openwrt.git

###For Barrier Breaker 14.07
git clone git://git.openwrt.org/14.07/openwrt.git

##Install Quilt
quilt is the tools OpenWrt used to manage patches. You need to install it before you use patches.
http://wiki.openwrt.org/doc/devel/patches 
`
sudo apt-get install quilt
`
Configure quilt according to openwrt docs.

`
cat > ~/.quiltrc <<EOF
QUILT_DIFF_ARGS="--no-timestamps --no-index -p ab --color=auto"
QUILT_REFRESH_ARGS="--no-timestamps --no-index -p ab"
QUILT_PATCH_OPTS="--unified"
QUILT_DIFF_OPTS="-p"
EDITOR="nano"
EOF
`

##Apply patches
`
cd openwrt
mkdir patches
cp [gl-ar150.patch series] patches
quilt push -a
`
