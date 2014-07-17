OpenvWrt
===================

Open vSwitch 2.1.2 (OvS) package for OpenWrt "Barrier Breaker" (trunk, r41432)

## Installation in OpenWrt

1. cd $TOPDIR

2. echo 'src-git openvswitch git://github.com/pichuang/openvwrt.git' >> feeds.conf

3. ./scripts/feeds update openvswitch

4. ./scripts/feeds install -a -p openvswitch

5. wget https://gist.githubusercontent.com/pichuang/7372af6d5d3bd1db5a88/raw/4e2290e3e184288de7623c02f63fb57c536e035a/openwrt-add-libatomic.patch -q -O - | patch -p1

6. make menuconfig
 * select Network -> openvswitch-switch, openvswitch-switch, openvswitch-ipsec (Optional)
 * select Advanced configuration options (for developers) -> Toolchain Options -> Binutils Version -> Linaro binutils 2.24
 * UNSELECT Advanced configuration options (for developers) -> Target Options -> Build packages with MIPS16 instructions

7. echo '#CONFIG_KERNEL_BRIDGE is not set' >> .config

8. make V=s

**!WARNING!** You need repeat step 7 and 8 after you enter "make menuconfig".


## Enviroment
* Hardware: D-LINK Dir-835
* Build enviroment
 * gcc version 4.9.0 20140604 (prerelease) (GCC)
 * ArchLinux x86_64

Q&A
---

1. How to build OpenWrt?
 * Please read [Roan's blog Compiled OpenWrt](http://roan.logdown.com/posts/165911-compiled-openwrt) 

2. How to set OpenvSwitch configuration?
 * Please read [Roan's blog Set OpenvSwitch](http://roan.logdown.com/posts/191801-set-openvswitch)

3. No works?
 * Try reboot and ```telnet 192.168.1.1```
 * or, ```make clean``` rebuild it.

Screenshot
----------

![alt tag](https://lh3.googleusercontent.com/-iG9uWyoYfs8/U7VMH6x69LI/AAAAAAAAE3o/LXO-6HelqrY/w1648-h1142-no/%25E8%259E%25A2%25E5%25B9%2595%25E5%25BF%25AB%25E7%2585%25A7+2014-07-03+20.24.39.png)

Development
-----------

Please fork on github and send pull requests.

