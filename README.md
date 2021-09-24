[![Build N1 61+o](https://github.com/MXJNZ6/Flippy-D/actions/workflows/N1.yml/badge.svg)](https://github.com/MXJNZ6/Flippy-D/actions/workflows/N1.yml) 
一：第一次刷入emmc: /root/install-to-emmc.sh

二：晶晨宝盒升级
ssh步骤的可视化插件，拥有在线，本地升级以及快照管理，备份等功能

三：在线ssh升级
1. cd /mnt/mmcblk2p4
2. wget【空格】tar.gz右键复制的releases里的固件下载连接
 2.1例： wget https://github.com/MXJNZ6/Flippy-D/releases/download/openwrt_s905d_n1_64-lean%26flippy%26lienol/openwrt_s905d_n1_R21.9.18_k5.4.148-flippy-64+o.img.gz
3. 解压 gzip -dv o【tab】（tab是自动补全）
 3.1例：gzip -dv oopenwrt_s905d_n1_R21.9.18_k5.4.148-flippy-64+o.img.gz
4. 同2下载 update-amlogic-openwrt.sh 升级脚本文件
5. 赋予脚本权限 chmod 755 update-amlogic-openwrt.sh
6. 输入./update-amlogic-openwrt.sh o【tab】

四：本地ssh升级除去无需下载步骤其它与三相同

快照功能:ssh链接后输入/usr/sbin/flippy

openwrt rootfs 编译注意事项：

       Target System  ->  QEMU ARM Virtual Machine 
       Subtarget ->  QEMU ARMv8 Virtual Machine (cortex-a53)
       Target Profile  ->  Default
       Target Images  ->   tar.gz
       *** 必选软件包(基础依赖包，仅保证打出的包可以写入EMMC,可以在EMMC上在线升级，不包含具体的应用)： 
       Languages -> Perl               
                    ->  perl-http-date
                    ->  perlbase-getopt
                    ->  perlbase-time
                    ->  perlbase-unicode                              
                    ->  perlbase-utf8        
       Utilities -> Disc -> blkid、fdisk、lsblk、parted            
                 -> Filesystem -> attr、btrfs-progs(Build with zstd support)、chattr、dosfstools、
                                  e2fsprogs、f2fs-tools、f2fsck、lsattr、mkf2fs、xfs-fsck、xfs-mkfs    
                 -> Shells  ->  bash         
                 -> gawk、getopt、losetup、tar、uuidgen

        * (可选)Wifi基础包：
        *     打出的包可支持博通SDIO无线模块,Firmware不用选，
        *     因为打包源码中已经包含了来自Armbian的firmware，
        *     会自动覆盖openwrt rootfs中已有的firmware
        Kernel modules  ->   Wireless Drivers -> kmod-brcmfmac(SDIO) 
                                              -> kmod-brcmutil
                                              -> kmod-cfg80211
                                              -> kmod-mac80211
        Network  ->  WirelessAPD -> hostpad-common
                                 -> wpa-cli
                                 -> wpad-basic
                 ->  iw
![2021-09-23_150152](https://user-images.githubusercontent.com/53927877/134467833-972ccb25-b9a7-4e69-a658-728a6ac75012.png)
![2021-09-23_150215](https://user-images.githubusercontent.com/53927877/134467838-8aa6c8b1-2cbe-4bf5-9694-7a9e6a11754b.png)
![2021-09-23_150321](https://user-images.githubusercontent.com/53927877/134467868-bd915143-694a-49bf-9eb1-2e91a57d3f3b.png)
![2021-09-23_150132](https://user-images.githubusercontent.com/53927877/134467811-466bef4c-37e9-44bc-96bc-a0cbef81e9e3.png)
![2021-09-23_150254](https://user-images.githubusercontent.com/53927877/134467842-74c9d0b6-82b0-4afe-b9d9-db8b437571a6.png)
![2021-09-23_150303](https://user-images.githubusercontent.com/53927877/134467850-d6201ee9-9a10-45f8-a529-729853c53681.png)
![2021-09-23_150314](https://user-images.githubusercontent.com/53927877/134467862-04ba79dc-ddf6-4ff0-9e1c-a084e45975f9.png)
![2021-09-23_150327](https://user-images.githubusercontent.com/53927877/134467873-c73510fb-c0dd-4bf6-854a-a8c47461caa0.png)

