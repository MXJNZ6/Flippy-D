[![Build N1 61+o](https://github.com/MXJNZ6/Flippy-D/actions/workflows/N1.yml/badge.svg)](https://github.com/MXJNZ6/Flippy-D/actions/workflows/N1.yml)
第一次刷入emmc: /root/install-to-emmc.sh
在线升级
1. cd /mnt/mmcblk2p4
2. wget img或者tar.gz右键复制的下载连接
3. 下载.gz的需要解压 gzip -dv o[tab]
4. chmod 755 update-amlogic-openwrt.sh
5. ./update-amlogic-openwrt.sh o[tab]
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

![1](https://user-images.githubusercontent.com/53927877/125562671-88397075-461e-4faa-b27e-164899ddd3fa.JPG)
![2](https://user-images.githubusercontent.com/53927877/125562684-0dd6aedd-6924-496f-95e3-f9aa32e0a61a.JPG)
![3](https://user-images.githubusercontent.com/53927877/125562696-2a47311f-6077-4a29-b3f9-07b3bfd01f69.JPG)
![4](https://user-images.githubusercontent.com/53927877/125562707-031b92de-ac69-432d-a27a-bd263e1f1ed4.JPG)
![5](https://user-images.githubusercontent.com/53927877/125562716-7ac6b995-8d4d-4c66-93f6-121872177c12.JPG)
![6](https://user-images.githubusercontent.com/53927877/125562722-e6cf1ad4-3c4a-4372-8332-c1792bc902f8.JPG)
