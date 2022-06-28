[![Build N1](https://github.com/MXJNZ6/Flippy-D/actions/workflows/N1.yml/badge.svg)](https://github.com/MXJNZ6/Flippy-D/actions/workflows/N1.yml)
```
Fork本仓库，在Settings-Actions-General最下边选择Read and write permissions和Allow GitHub Actions to create and approve pull requests
N1.yml介绍
1. 37行是内核文件下载途径
2. 38行是f大打包脚本下载途径
4. 45行是下载rootfs文件途径，修改MXJNZ6/openwrt为你的仓库，Aarch64修改为你的仓库releases文件的tag标签
5. 69行为打包命令根据设备不同可根据需求更改
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
### Wireguard使用教程
```
以N1旁路由为例
主路由DDNS域名为n1.pangluyou.xyz
N1的ip地址为10.10.10.254
主路由端口映射公网的12345端口到N1的51820
根据自己的需求更改下边
第三行的WG_HOST等于号后边为自己的域名、
第四行的WG_PORT等于号后边的公网端口号为自己端口映射的、
第五行的PASSWORD后边是本地web管理界面的密码、
第六行的WG_DEFAULT_DNS的值代表客户端的dns服务器推荐设置为N1的ip
下边的命令不要带$号。
```

<pre>
docker run -d \
--name=WG \
-e WG_HOST=n1.pangluyou.xyz \
-e WG_PORT=12345 \
-e PASSWORD=123456 \
-e WG_DEFAULT_DNS=10.10.10.254 \
-e WG_PERSISTENT_KEEPALIVE=25 \
-v /mnt/mmcblk2p4/wireguard:/etc/wireguard \
-p 51820:51820/udp \
-p 51821:51821/tcp \
--cap-add=NET_ADMIN \
--cap-add=SYS_MODULE \
--sysctl="net.ipv4.conf.all.src_valid_mark=1" \
--sysctl="net.ipv4.ip_forward=1" \
--restart unless-stopped \
weejewel/wg-easy
</pre>

浏览器输入N1的ip+51821进入管理界面.例：`http://10.10.10.254:51821`.

## 选项

这些选项可以通过 -e KEY="VALUE"在 docker run 命令中设置环境变量来配置.

| Env | Default | Example | Description |
| - | - | - | - |
| `PASSWORD` | - | `123456` | 设置后需要密码登录. |
| `WG_HOST` | - | `vpn.myserver.com` | 动态域名DDNS. |
| `WG_PORT` | `51820` | `12345` | VPN 服务器的公共UDP端口. WireGuard 将始终在 Docker 容器内进行侦听 51820 端口. |
| `WG_MTU` | `null` | `1420` | 客户端将使用的 MTU .服务器使用默认的 WG MTU. |
| `WG_PERSISTENT_KEEPALIVE` | `0` | `25` | 以秒为单位保持“连接”打开的值. |
| `WG_DEFAULT_ADDRESS` | `10.8.0.x` | `10.6.0.x` | 客户端 IP 地址范围. |
| `WG_DEFAULT_DNS` | `1.1.1.1` | `8.8.8.8, 8.8.4.4` | 客户端将使用 DNS 服务器. |
| `WG_ALLOWED_IPS` | `0.0.0.0/0, ::/0` | `192.168.15.0/24, 10.0.1.0/24` | 允许的 IP 客户端. |
| `WG_POST_UP` | `...` | `iptables ...` | 有关默认值，请参见 [config.js](https://github.com/WeeJeWel/wg-easy/blob/master/src/config.js#L19) . |
| `WG_POST_DOWN` | `...` | `iptables ...` | 有关默认值，请参见 [config.js](https://github.com/WeeJeWel/wg-easy/blob/master/src/config.js#L26) . |

# 更新

```bash
docker stop WG
docker rm WG
docker pull mlf001/wg-easy:nightly
```

再次运行 `docker run -d \ ...` 此处省略号代表的是上边38-53行的命令在输入一遍，而不是真的是三个点.
