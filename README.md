[![Build N1 61+o](https://github.com/MXJNZ6/Flippy-D/actions/workflows/N1.yml/badge.svg)](https://github.com/MXJNZ6/Flippy-D/actions/workflows/N1.yml) 
打包脚本及相关介绍: 
1. workflows里N1.yml的40行为检测releases里的最新rootfs文件可自定义MXJNZ6/OpenWrt-D为自己或者其他人的编译仓库
2. 48行下载f大打包脚本
3. 49行下载内核文件，当前为ophub的内核仓库，可自定义。如果自定义需要修改每一个whoami文件里的第三行KERNEL_PKG_HOME="/opt/kernel/pub/stable/5.4.159"中的相应途径
4. 58行为下载rootfs文件途径，修改MXJNZ6/OpenWrt-D为与40行同一仓库
5. 82行为打包命令，根据需求更改.
