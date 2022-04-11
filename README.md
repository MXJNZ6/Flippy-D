[![Build N1 61+o](https://github.com/MXJNZ6/Flippy-D/actions/workflows/N1.yml/badge.svg)](https://github.com/MXJNZ6/Flippy-D/actions/workflows/N1.yml).
```
N1.yml介绍(需要在settings里填写RELEASES_TOKEN)
1. 39行为检测releases里的最新rootfs文件可自定义MXJNZ6/OpenWrt-D为自己或者其他人的编译仓库
2. 48行是内核文件下载途径
3. 49行是f大打包脚本下载途径
4. 57行为下载rootfs文件途径，修改MXJNZ6/OpenWrt-D为与39行同一仓库
5. 81行为打包命令根据设备不同可根据需求更改
6. 22-29行是几个任务流程，比如我只需要5.15那么你可以把其它的都删除，如果需要其它的可以在类比文件结构新建一个
```
```
whoami文件介绍
1. 第1行你自己可以想一个拉风的代号
2. 第2行为openwrt相关版本号
3. 第3行为linux内核版本号
4. 第4行为F大内核打包版本
5. 第5行为内核全称
6. 第6行为内核途径
7. 如f大内核更新，想编译最新版只需更改第3和第4行就行。第二行可修改与F大或者lean一致，也可修改成自己喜欢的
```
![插件](https://user-images.githubusercontent.com/53927877/162709856-d6454dd1-dcce-462c-8dd6-d026d8723d9b.png)
