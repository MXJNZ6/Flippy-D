[![Build N1 61+o](https://github.com/MXJNZ6/Flippy-D/actions/workflows/N1.yml/badge.svg)](https://github.com/MXJNZ6/Flippy-D/actions/workflows/N1.yml).

N1.yml介绍(需要在settings里填写RELEASES_TOKEN)
1. 39行为检测releases里的最新rootfs文件可自定义MXJNZ6/OpenWrt-D为自己或者其他人的编译仓库
2. 47行下载f大打包脚本
3. 48行下载内核文件，当前为ophub（https://github.com/ophub/kernel ）的内核仓库，可自定义。如果自定义需要修改每一个whoami文件里的第5行/opt/kernel/pub/stable为相应途径
4. 57行为下载rootfs文件途径，修改MXJNZ6/OpenWrt-D为与39行同一仓库
5. 80行为打包命令，根据需求更改.
6. 22-29行为任务流程，比如我只需要5.4那么你可以把5.10 5.15 5.15的都删除，如果你还有其它的比如5.20那你可以新建一个5.20文件夹，文件夹结构与其它文件夹一样，修改whoami里对应的地方并在5.15下边添加对应任务

whoami文件介绍
1. 第1行为作者
2. 第2行为内核发行号
3. 第3行为f大内核版本号
4. 第4行为内核具体名称
5. 第5行为内核文件途径
6. 如f大内核更新编译最新版只需更改第2和3行就行
