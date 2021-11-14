[![Build N1 61+o](https://github.com/MXJNZ6/Flippy-D/actions/workflows/N1.yml/badge.svg)](https://github.com/MXJNZ6/Flippy-D/actions/workflows/N1.yml) 
一、打包脚本及相关介绍: 
1. workflows里N1.yml的40行为检测releases里的最新rootfs文件可自定义MXJNZ6/OpenWrt-D为自己或者其他人的编译仓库
2. 48行下载f大打包脚本
3. 49行下载内核文件，当前为ophub的内核仓库，可自定义。如果自定义需要修改每一个whoami文件里的第三行KERNEL_PKG_HOME="/opt/kernel/pub/stable/5.4.159"中的相应途径
4. 58行为下载rootfs文件途径，修改MXJNZ6/OpenWrt-D为与40行同一仓库
5. 82行为打包命令，根据需求更改.
![2021-09-23_150152](https://user-images.githubusercontent.com/53927877/134467833-972ccb25-b9a7-4e69-a658-728a6ac75012.png)
![2021-09-23_150215](https://user-images.githubusercontent.com/53927877/134467838-8aa6c8b1-2cbe-4bf5-9694-7a9e6a11754b.png)
![2021-09-23_150321](https://user-images.githubusercontent.com/53927877/134467868-bd915143-694a-49bf-9eb1-2e91a57d3f3b.png)
![2021-09-23_150132](https://user-images.githubusercontent.com/53927877/134467811-466bef4c-37e9-44bc-96bc-a0cbef81e9e3.png)
![2021-09-23_150254](https://user-images.githubusercontent.com/53927877/134467842-74c9d0b6-82b0-4afe-b9d9-db8b437571a6.png)
![2021-09-23_150303](https://user-images.githubusercontent.com/53927877/134467850-d6201ee9-9a10-45f8-a529-729853c53681.png)
![2021-09-23_150314](https://user-images.githubusercontent.com/53927877/134467862-04ba79dc-ddf6-4ff0-9e1c-a084e45975f9.png)
![2021-09-23_150327](https://user-images.githubusercontent.com/53927877/134467873-c73510fb-c0dd-4bf6-854a-a8c47461caa0.png)

