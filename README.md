[![Build N1](https://github.com/MXJNZ6/Flippy-D/actions/workflows/N1.yml/badge.svg)](https://github.com/MXJNZ6/Flippy-D/actions/workflows/N1.yml)
```
Fork本仓库，在Settings-Actions-General最下边选择Read and write permissions和Allow GitHub Actions to create and approve pull requests
N1.yml介绍
1. 31行是检测releases里的最新rootfs文件可自定义MXJNZ6/OpenWrt-D为自己或者其他人的编译仓库
2. 39行是内核文件下载途径
3. 40行是f大打包脚本下载途径
4. 47行是下载rootfs文件途径，修改MXJNZ6/OpenWrt-D为与39行同一仓库
5. 71行为打包命令根据设备不同可根据需求更改
6. 21-22行是几个任务流程，比如我只需要5.15那么你可以把其它的都删除，如果需要其它的可以在类比5.15和5.17文件结构新建一个
```
```
whoami文件介绍
1. 第1行你自己可以想一个拉风的代号。比如Akatsuki改为aoteman
2. 第2行是openwrt相关版本号。比如R22.5.1改成R666888
3. 第3行是linux内核版本号，一般设置为最新内核。比如5.15.36
4. 第4行是F大内核打包版本，一般设置为最新版本。比如72+o/72+
5. 第5行是内核全称。不需要动
6. 第6行是内核途径。不需要动
7. 如f大内核更新，想编译最新版只需更改第3和第4行就行。
```
![插件](https://user-images.githubusercontent.com/53927877/162709856-d6454dd1-dcce-462c-8dd6-d026d8723d9b.png)
