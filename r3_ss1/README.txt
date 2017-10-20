https://gist.github.com/luojixinhao/a77ad95329e0bf2c4ccdbc3bf952e64b
https://gist.github.com/rambolee/468ee988d2cf80224a6ac4675c141b4f

https://cokebar.info/archives/962

起因

因为，希望要让Apple TV能够直接访问Youtube。如果在路由器不翻墙的情况，即使直接通过手机AirPlay也是无法直接投影Youbute等墙外的信息的。 必须Apple TV本身的链路能够访问Youtube才行。

因此，这说明了Airplay的协议是传递的访问「地址」而非直接推送视频镜像流。

升级到开发版

下载开发版rom

从小米官网下载相关开发版ROM，这样是支持SSH的。对应地址http://www1.miwifi.com/miwifi_download.html

升级到开发版rom

直接访问 http://miwifi.com 登录后选择升级系统，并选择手工升级。

选择直接从文件中（即刚才下载的rom文件），类似miwifi_r3_all_55ac7_2.11.20.bin。 -- 截止到目前（2017年03月21日），最合适的版本是之前比较旧的。miwifi_r3_all_55ac7_2.11.20.bin这个版本。

在我自己的VPS中备份一个bin文件。

一定要注意版本，目前，测试最新版本。例如miwifi_r3_firmware_e87c6_2.13.75.bin可以从官网下载到的。或者，直接通过后台管理页面升级到的「最新版」都是无法使用当前的「破解」支持SSH的方法。

点击「升级」，期间路由器会重启。为了保证清理干净，建议直接选择「不保留配置」。虽然这样会导致需要重新配置宽带帐号，但是，避免了配置文件降级（目前，开发版的版本号是低于发行版的版本号的--我也不知道这个是什么逻辑）。

重启后，等待路由器的指示灯重新变成「蓝色」，即可以连接一个没有密码的设置的Miwifi信号。

注意，不要这么操作了。证明这样是不行的

重新登录 http://miwifi.com 在系统配置中，检查一下，是否有新的开发版本支持。本次，我就碰到官网中显示的开发版，并不是最新版。导致我还需要进行一次「自动升级」

重新配置上网帐号

连接到Miwifi信号后，按照Wizard提示，配置宽带帐号和Wifi SSID后。等待路由重启后，如果SSID和Password与刷机之前没有变化，那么，相关的所有设备可以自动重新连接到路由器上。

破解ssh登录

前提，下面描述的方法针对的条件如下：

硬件：小米路由器3
系统：MiWiFi 开发版 2.11.20，对应文件：miwifi_r3_all_55ac7_2.11.20.bin ; 备份地址
通过访问4个一系列的URL，crack SSH。具体Link如下。在操作过程中需要注意：

**登录管理页面，替换stok后陆续在地址栏执行以下4条（注意每次执行要等待指令执行完成后，即页面打开状态的小圆圈转完）。 **

http://192.168.31.1/cgi-bin/luci/;stok=【你的stok，登录路由器管理界面在地址栏可以看到】/api/xqnetwork/set_wifi_ap?ssid=tianbao&encryption=NONE&enctype=NONE&channel=1%3Bnvram%20set%20ssh%5Fen%3D1%3B%20nvram%20commit


http://192.168.31.1/cgi-bin/luci/;stok=【你的stok，登录路由器管理界面在地址栏可以看到】/api/xqnetwork/set_wifi_ap?ssid=tianbao&encryption=NONE&enctype=NONE&channel=1%3Bsed%20%2Di%20%22%3Ax%3AN%3As%2Fif%20%5C%5B%2E%2A%5C%3B%20then%5Cn%2E%2Areturn%200%5Cn%2E%2Afi%2F%23tb%2F%3Bb%20x%22%20%2Fetc%2Finit.d%2Fdropbear


http://192.168.31.1/cgi-bin/luci/;stok=【你的stok，登录路由器管理界面在地址栏可以看到】/api/xqnetwork/set_wifi_ap?ssid=tianbao&encryption=NONE&enctype=NONE&channel=1%3B%2Fetc%2Finit.d%2Fdropbear%20start


http://192.168.31.1/cgi-bin/luci/;stok=【你的stok，登录路由器管理界面在地址栏可以看到】/api/xqsystem/set_name_password?oldPwd=路由器管理密码&newPwd=路由器管理密码 
前三个URL返回的相关错误代码是：

{
    "msg": "未能连接到指定WiFi(Probe timeout)",
    "code": 1616
}
最后一个是root ssh登录小米路由器的密码设置，因此，只有返回如下，才能说明ssh破解正常：

{
    "code": 0
}
安装配置 Shadowsocks

使用一键安装脚本

参考：https://github.com/JeansHuang/miwifi-ss

cd /userdisk && rm -rf miwifi.sh && wget http://7xo6sw.com1.z0.glb.clouddn.com/miwifi.sh && chmod +x miwifi.sh && sh ./miwifi.sh
其中，miwifi.sh 的访问地址可以根据具体情况调整，我使用的文件内容如下：

#!/bin/sh
cd /tmp
echo "*********************************************************"
echo "*                    SS插件安装器                         *"
echo "*                                                       *"
echo "*          安装前请关闭小米路由器自带VPN功能                  *"
echo "*                                                       *"
echo "*         支持路由型号：mini | r1d | r2d | r3              *"
echo "*                                                       *"
echo "*     没SS帐号？这里：http://bbs.xiaomi.cn/t-13066771      *"
echo "*                                                       *"
echo "*********************************************************"
echo "                                                         "
echo "请选择需要的操作（按下对应数字后回车确认）"
echo "1：安装r1d&r2d版SS插件"
echo "2：卸载r1d&r2d版SS插件"
echo "3：安装mini版ss插件"
echo "4：卸载mini版ss插件"
echo "5：安装r3版ss插件"
echo "6：卸载r3版ss插件"
echo "0:退出"
read num

if [ "${num}" == "1" ]
then
cd /tmp
rm -rf *.sh
wget http://7xo6sw.com1.z0.glb.clouddn.com/r2d_ss.sh
chmod -R 777 r2d_ss.sh
./r2d_ss.sh
fi
if [ "${num}" == "2" ]
then
cd /tmp
rm -rf *.sh
wget http://7xo6sw.com1.z0.glb.clouddn.com/r2d_uninstall.sh
chmod -R 777 r2d_uninstall.sh
./r2d_uninstall.sh
fi


if [ "${num}" == "3" ]
then
cd /tmp
rm -rf *.sh
wget http://7xo6sw.com1.z0.glb.clouddn.com/mini_ss.sh
chmod -R 777 mini_ss.sh
./mini_ss.sh
fi

if [ "${num}" == "4" ]
then
cd /tmp
rm -rf *.sh
wget http://7xo6sw.com1.z0.glb.clouddn.com/mini_uninstall.sh
chmod -R 777 mini_uninstall.sh
sh mini_uninstall.sh
fi

if [ "${num}" == "5" ]
then
cd /tmp
rm -rf *.sh
wget http://7xo6sw.com1.z0.glb.clouddn.com/r3_ss.sh
chmod -R 777 r3_ss.sh
./r3_ss.sh
fi

if [ "${num}" == "6" ]
then
cd /tmp
rm -rf *.sh
wget http://7xo6sw.com1.z0.glb.clouddn.com/r3_uninstall.sh
chmod -R 777 r3_uninstall.sh
sh r3_uninstall.sh
fi

if [ "${num}" == "0" ]
then
exit
fi
核心脚本 r3_ss.sh 和 r3_uninstall.sh

r3_ss.sh

#!/bin/sh

clear
echo "#############################################################"
echo "# Install Shadowsocks for Miwifi(r3)"
echo "#############################################################"

# Make sure only root can run our script
if [[ $EUID -ne 0 ]]; then
   echo "Error:This script must be run as root!" 1>&2
   exit 1
fi
cd /tmp
rm -f shadowsocks_r3.tar.gz
wget http://7xo6sw.com1.z0.glb.clouddn.com/shadowsocks_r3.tar.gz
tar zxf shadowsocks_r3.tar.gz

# install shadowsocks ss-redir to /data/usr/sbin
mkdir -p /data/usr/sbin
cp -f ./shadowsocks_r3/ss-redir  /data/usr/sbin/ss-redir
chmod +x /data/usr/sbin/ss-redir

# Config shadowsocks init script
cp ./shadowsocks_r3/shadowsocks /etc/init.d/shadowsocks
chmod +x /etc/init.d/shadowsocks

#config setting and save settings.
echo "#############################################################"
echo "#"
echo "# Please input your shadowsocks configuration"
echo "#"
echo "#############################################################"
echo ""
echo "请输入服务器IP:"
read serverip
echo "请输入服务器端口:"
read serverport
echo "请输入密码:"
read shadowsockspwd
echo "请输入加密方式"
read method

# Config shadowsocks
cat > /etc/shadowsocks.json<<-EOF
{
  "server":"${serverip}",
  "server_port":${serverport},
  "local_address":"127.0.0.1",
  "local_port":1081,
  "password":"${shadowsockspwd}",
  "timeout":600,
  "method":"${method}"
}
EOF

#config dnsmasq
cp -f ./shadowsocks_r3/dnsmasq_list.conf /etc/dnsmasq.d/dnsmasq_list.conf

#config firewall
cp -f /etc/firewall.user /etc/firewall.user.back
echo "ipset -N gfwlist iphash -! " >> /etc/firewall.user
echo "iptables -t nat -A PREROUTING -p tcp -m set --match-set gfwlist dst -j REDIRECT --to-port 1081" >> /etc/firewall.user

#restart all service
/etc/init.d/dnsmasq restart
/etc/init.d/firewall restart
/etc/init.d/shadowsocks start
/etc/init.d/shadowsocks enable

#install successfully
rm -rf /tmp/shadowsocks_r3
rm -f /tmp/shadowsocks_r3.tar.gz
echo ""
echo "Shadowsocks安装成功！"
echo ""
exit 0
此处备份一下 shadowsocks_r3.tar.gz shadowsocks_r3.tar.gz

echo "开始卸载Shadowsocks"
echo -e "停止相关进程--------------------------------------\c"
/etc/init.d/shadowsocks stop 1>/dev/null 2>&1
/etc/init.d/shadowsocks disable 1>/dev/null 2>&1
echo -e "[\e[32m完成\e[37m]"
echo -e "删除相关文件--------------------------------------\c"
rm -rf /etc/init.d/shadowsocks
rm -rf /etc/dnsmasq.d/dnsmasq_list.conf
rm -rf /data/usr/sbin
rm -rf /etc/shadowsocks.json
sed -i '/ipset -N gfwlist iphash -!/d' /etc/firewall.user
sed -i '/iptables -t nat -A PREROUTING -p tcp -m set --match-set gfwlist dst -j REDIRECT --to-port 1081/d' /etc/firewall.user
/etc/init.d/firewall restart
/etc/init.d/dnsmasq restart
echo "卸载Shadowsocks完成"
cd /tmp && rm -rf *.sh && wget http://7xo6sw.com1.z0.glb.clouddn.com/miwifi.sh && sh ./miwifi.sh && rm -rf *.sh
脚本都做了什么

获取 shadowsocks_r3.tar.gz
安装 ss-redir
配置 init.d shadowsocks
配置 shadowsocks.json
配置 dnsmasq
配置 iptables
重启服务
补充

升级到新版的ROM

我并没有选择让小米路由器自己升级到最新的ROM。但是，第二天早晨起来后，小米路由器确实升级到了最新的版本。当前版本号是：MiWiFi 开发版 2.19.65。

还好SSH登录的破解还是生效被保留下来了。

导致的问题就是，shadowsocks 服务丢失了。需要自己重新跑脚本进行安装。

性能问题

对比之前老的初代高性能版的小米路由器，现在只有128Mb的小米路由3，每次打开web控制面板，都能发现会导致CPU短期100%。

整体性能感觉都是很一般。后续不知道我是否加入NAS后是否需要考虑一个性能更好的路由器进行配合了。

后续(Todo-List)：

自动更新 dnsmasq conf

参考相关

脚本
Shadowsocks + GfwList 实现 OpenWRT / LEDE 路由器自动翻墙
GFWlist+ShadowSocks实现路由器透明代理
shadowsock luci-app-shadowsocks GFWlist support
附录：

参考连接

小米路由器3最新开启SSH与安装Shadowsocks方法（7月19日）
miwifi-ss
小米路由器3 SSH + 一键SS 教程 （本禁文章）
印象笔记:重新折腾小米路由器3的shadowsocks（成功搞定）
如何让小米路由器聪明的使用shadowsocks
https://github.com/blademainer/miwifi-ss
https://github.com/boxcore/miwifi-ss/blob/master/r3_ss.sh
https://github.com/poodarchu/miwifi_ss/blob/master/miwifi.sh
[经验技巧] 小米路由器一键安装Shadowsocks教程(支持全型号)
shadowsocks在CentOS7和小米路由器mini上的应用
小米路由器如何开启Shadowsocks支持
