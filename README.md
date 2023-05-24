# 8211ac

Drivers rtl8812au-ac with `hostapd` support from https://github.com/immortalwrt/immortalwrt

## Requirements

- RAM >= 8 Gb
- Docker

## How to use

Use with openwrt v22.03.5

`git clone https://github.com/x0rium/8211ac.git rtl8812au-ac`

Copy this files in package/kernel/rtl8812au-ac/

`cp -r  rtl8812au-ac ./package/kernel/`

Run Docker image build 

`./owrtbuild init v22.03.5`

`make menuconfig`

- Target System (x86)
- Subtarget (x86_64)
- Target Profile (Generic x86/64)
- Kernel modules  ---> Wireless Drivers  ---> kmod-mac80211
- Kernel modules  ---> Wireless Drivers  ---> kmod-rtl8812au-ac

`make -j$(nproc) kernel_menuconfig`

`make -j$(nproc) defconfig download clean world V=sc` 

Answer on all questions "N" 

Coffeee ) 

ls ./bin/targets/x86/64/

```
drwxr-xr-x  1 build build 4.0K May 24 01:28 .
drwxr-xr-x  1 build build 4.0K May 24 00:36 ..
-rw-r--r--  1 build build 233K May 24 01:10 .config
drwxr-xr-x  1 build build 4.0K May 24 00:46 .git
-rw-r--r--  1 build build    8 May 23 21:55 .gitattributes
drwxr-xr-x  1 build build 4.0K May 23 21:55 .github
-rw-r--r--  1 build build  311 May 23 21:55 .gitignore
-rw-r--r--  1 build build  106 May 23 21:55 BSDmakefile
-rw-r--r--  1 build build  284 May 23 21:55 COPYING
-rw-r--r--  1 build build  668 May 23 21:55 Config.in
drwxr-xr-x  2 build build 4.0K May 23 21:55 LICENSES
-rw-r--r--  1 build build 4.0K May 23 21:55 Makefile
-rw-r--r--  1 build build 3.6K May 23 21:55 README.md
drwxr-xr-x  1 build build 4.0K May 24 01:23 bin
drwxr-xr-x  6 build build 4.0K May 24 01:23 build_dir
drwxr-xr-x  1 build build 4.0K May 23 21:55 config
drwxr-xr-x  2 build build 4.0K May 24 01:25 dl
drwxr-xr-x 10 build build 4.0K May 24 00:23 feeds
-rw-r--r--  1 build build  415 May 23 21:55 feeds.conf.default
drwxr-xr-x  1 build build 4.0K May 23 21:55 include
-rw-r--r--  1 build build  176 May 24 01:28 key-build
-rw-r--r--  1 build build   92 May 24 01:28 key-build.pub
-rw-r--r--  1 build build  356 May 24 01:28 key-build.ucert
-rw-r--r--  1 build build  260 May 24 01:28 key-build.ucert.revoke
drwxr-xr-x  1 build build 4.0K May 24 00:23 package
-rw-r--r--  1 build build  15K May 23 21:55 rules.mk
drwxr-xr-x  1 build build 4.0K May 23 21:55 scripts
drwxr-xr-x  1 build build 4.0K May 24 01:31 staging_dir
drwxr-xr-x  1 build build 4.0K May 23 21:55 target
drwxr-xr-x  1 build build  12K May 24 01:31 tmp
drwxr-xr-x  1 build build 4.0K May 23 21:55 toolchain
drwxr-xr-x  1 build build 4.0K May 23 21:55 tools
-rw-r--r--  1 build build   18 May 23 21:55 version
-rw-r--r--  1 build build   11 May 23 21:55 version.date
```

to copy from container open new terminal tab and use `docker cp` command.

https://docs.docker.com/engine/reference/commandline/cp/

Congrats!
