[![Build N1 61+o](https://github.com/MXJNZ6/Flippy-D/actions/workflows/N1.yml/badge.svg)](https://github.com/MXJNZ6/Flippy-D/actions/workflows/N1.yml) 
N1.yml介绍
1. 39行为检测releases里的最新rootfs文件可自定义MXJNZ6/OpenWrt-D为自己或者其他人的编译仓库
2. 47行下载f大打包脚本
3. 48行下载内核文件，当前为ophub的内核仓库，可自定义。如果自定义需要修改每一个whoami文件里的第三行KERNEL_PKG_HOME="/opt/kernel/pub/stable/5.4.159"中的相应途径
4. 57行为下载rootfs文件途径，修改MXJNZ6/OpenWrt-D为与40行同一仓库
5. 80行为打包命令，根据需求更改.

whoami文件介绍
1. 第1行为作者
2. 第2行为内核发行号
3. 第3行为f大内核版本号
4. 第4行为内核具体名称
5. 第5行为内核文件途径
6. 如f大内核更新编译最新版只需更改第2和3行就行
