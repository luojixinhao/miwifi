https://gist.github.com/luojixinhao/a77ad95329e0bf2c4ccdbc3bf952e64b
https://gist.github.com/rambolee/468ee988d2cf80224a6ac4675c141b4f

https://cokebar.info/archives/962

����

��Ϊ��ϣ��Ҫ��Apple TV�ܹ�ֱ�ӷ���Youtube�������·��������ǽ���������ʹֱ��ͨ���ֻ�AirPlayҲ���޷�ֱ��ͶӰYoubute��ǽ�����Ϣ�ġ� ����Apple TV�������·�ܹ�����Youtube���С�

��ˣ���˵����Airplay��Э���Ǵ��ݵķ��ʡ���ַ������ֱ��������Ƶ��������

������������

���ؿ�����rom

��С�׹���������ؿ�����ROM��������֧��SSH�ġ���Ӧ��ַhttp://www1.miwifi.com/miwifi_download.html

������������rom

ֱ�ӷ��� http://miwifi.com ��¼��ѡ������ϵͳ����ѡ���ֹ�������

ѡ��ֱ�Ӵ��ļ��У����ղ����ص�rom�ļ���������miwifi_r3_all_55ac7_2.11.20.bin�� -- ��ֹ��Ŀǰ��2017��03��21�գ�������ʵİ汾��֮ǰ�ȽϾɵġ�miwifi_r3_all_55ac7_2.11.20.bin����汾��

�����Լ���VPS�б���һ��bin�ļ���

һ��Ҫע��汾��Ŀǰ���������°汾������miwifi_r3_firmware_e87c6_2.13.75.bin���Դӹ������ص��ġ����ߣ�ֱ��ͨ����̨����ҳ���������ġ����°桹�����޷�ʹ�õ�ǰ�ġ��ƽ⡹֧��SSH�ķ�����

��������������ڼ�·������������Ϊ�˱�֤����ɾ�������ֱ��ѡ�񡸲��������á�����Ȼ�����ᵼ����Ҫ�������ÿ���ʺţ����ǣ������������ļ�������Ŀǰ��������İ汾���ǵ��ڷ��а�İ汾�ŵ�--��Ҳ��֪�������ʲô�߼�����

�����󣬵ȴ�·������ָʾ�����±�ɡ���ɫ��������������һ��û����������õ�Miwifi�źš�

ע�⣬��Ҫ��ô�����ˡ�֤�������ǲ��е�

���µ�¼ http://miwifi.com ��ϵͳ�����У����һ�£��Ƿ����µĿ����汾֧�֡����Σ��Ҿ�������������ʾ�Ŀ����棬���������°档�����һ���Ҫ����һ�Ρ��Զ�������

�������������ʺ�

���ӵ�Miwifi�źź󣬰���Wizard��ʾ�����ÿ���ʺź�Wifi SSID�󡣵ȴ�·�����������SSID��Password��ˢ��֮ǰû�б仯����ô����ص������豸�����Զ��������ӵ�·�����ϡ�

�ƽ�ssh��¼

ǰ�ᣬ���������ķ�����Ե��������£�

Ӳ����С��·����3
ϵͳ��MiWiFi ������ 2.11.20����Ӧ�ļ���miwifi_r3_all_55ac7_2.11.20.bin ; ���ݵ�ַ
ͨ������4��һϵ�е�URL��crack SSH������Link���¡��ڲ�����������Ҫע�⣺

**��¼����ҳ�棬�滻stok��½���ڵ�ַ��ִ������4����ע��ÿ��ִ��Ҫ�ȴ�ָ��ִ����ɺ󣬼�ҳ���״̬��СԲȦת�꣩�� **

http://192.168.31.1/cgi-bin/luci/;stok=�����stok����¼·������������ڵ�ַ�����Կ�����/api/xqnetwork/set_wifi_ap?ssid=tianbao&encryption=NONE&enctype=NONE&channel=1%3Bnvram%20set%20ssh%5Fen%3D1%3B%20nvram%20commit


http://192.168.31.1/cgi-bin/luci/;stok=�����stok����¼·������������ڵ�ַ�����Կ�����/api/xqnetwork/set_wifi_ap?ssid=tianbao&encryption=NONE&enctype=NONE&channel=1%3Bsed%20%2Di%20%22%3Ax%3AN%3As%2Fif%20%5C%5B%2E%2A%5C%3B%20then%5Cn%2E%2Areturn%200%5Cn%2E%2Afi%2F%23tb%2F%3Bb%20x%22%20%2Fetc%2Finit.d%2Fdropbear


http://192.168.31.1/cgi-bin/luci/;stok=�����stok����¼·������������ڵ�ַ�����Կ�����/api/xqnetwork/set_wifi_ap?ssid=tianbao&encryption=NONE&enctype=NONE&channel=1%3B%2Fetc%2Finit.d%2Fdropbear%20start


http://192.168.31.1/cgi-bin/luci/;stok=�����stok����¼·������������ڵ�ַ�����Կ�����/api/xqsystem/set_name_password?oldPwd=·������������&newPwd=·������������ 
ǰ����URL���ص���ش�������ǣ�

{
    "msg": "δ�����ӵ�ָ��WiFi(Probe timeout)",
    "code": 1616
}
���һ����root ssh��¼С��·�������������ã���ˣ�ֻ�з������£�����˵��ssh�ƽ�������

{
    "code": 0
}
��װ���� Shadowsocks

ʹ��һ����װ�ű�

�ο���https://github.com/JeansHuang/miwifi-ss

cd /userdisk && rm -rf miwifi.sh && wget http://7xo6sw.com1.z0.glb.clouddn.com/miwifi.sh && chmod +x miwifi.sh && sh ./miwifi.sh
���У�miwifi.sh �ķ��ʵ�ַ���Ը��ݾ��������������ʹ�õ��ļ��������£�

#!/bin/sh
cd /tmp
echo "*********************************************************"
echo "*                    SS�����װ��                         *"
echo "*                                                       *"
echo "*          ��װǰ��ر�С��·�����Դ�VPN����                  *"
echo "*                                                       *"
echo "*         ֧��·���ͺţ�mini | r1d | r2d | r3              *"
echo "*                                                       *"
echo "*     ûSS�ʺţ����http://bbs.xiaomi.cn/t-13066771      *"
echo "*                                                       *"
echo "*********************************************************"
echo "                                                         "
echo "��ѡ����Ҫ�Ĳ��������¶�Ӧ���ֺ�س�ȷ�ϣ�"
echo "1����װr1d&r2d��SS���"
echo "2��ж��r1d&r2d��SS���"
echo "3����װmini��ss���"
echo "4��ж��mini��ss���"
echo "5����װr3��ss���"
echo "6��ж��r3��ss���"
echo "0:�˳�"
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
���Ľű� r3_ss.sh �� r3_uninstall.sh

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
echo "�����������IP:"
read serverip
echo "������������˿�:"
read serverport
echo "����������:"
read shadowsockspwd
echo "��������ܷ�ʽ"
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
echo "Shadowsocks��װ�ɹ���"
echo ""
exit 0
�˴�����һ�� shadowsocks_r3.tar.gz shadowsocks_r3.tar.gz

echo "��ʼж��Shadowsocks"
echo -e "ֹͣ��ؽ���--------------------------------------\c"
/etc/init.d/shadowsocks stop 1>/dev/null 2>&1
/etc/init.d/shadowsocks disable 1>/dev/null 2>&1
echo -e "[\e[32m���\e[37m]"
echo -e "ɾ������ļ�--------------------------------------\c"
rm -rf /etc/init.d/shadowsocks
rm -rf /etc/dnsmasq.d/dnsmasq_list.conf
rm -rf /data/usr/sbin
rm -rf /etc/shadowsocks.json
sed -i '/ipset -N gfwlist iphash -!/d' /etc/firewall.user
sed -i '/iptables -t nat -A PREROUTING -p tcp -m set --match-set gfwlist dst -j REDIRECT --to-port 1081/d' /etc/firewall.user
/etc/init.d/firewall restart
/etc/init.d/dnsmasq restart
echo "ж��Shadowsocks���"
cd /tmp && rm -rf *.sh && wget http://7xo6sw.com1.z0.glb.clouddn.com/miwifi.sh && sh ./miwifi.sh && rm -rf *.sh
�ű�������ʲô

��ȡ shadowsocks_r3.tar.gz
��װ ss-redir
���� init.d shadowsocks
���� shadowsocks.json
���� dnsmasq
���� iptables
��������
����

�������°��ROM

�Ҳ�û��ѡ����С��·�����Լ����������µ�ROM�����ǣ��ڶ����糿������С��·����ȷʵ�����������µİ汾����ǰ�汾���ǣ�MiWiFi ������ 2.19.65��

����SSH��¼���ƽ⻹����Ч�����������ˡ�

���µ�������ǣ�shadowsocks ����ʧ�ˡ���Ҫ�Լ������ܽű����а�װ��

��������

�Ա�֮ǰ�ϵĳ��������ܰ��С��·����������ֻ��128Mb��С��·��3��ÿ�δ�web������壬���ܷ��ֻᵼ��CPU����100%��

�������ܸо����Ǻ�һ�㡣������֪�����Ƿ����NAS���Ƿ���Ҫ����һ�����ܸ��õ�·������������ˡ�

����(Todo-List)��

�Զ����� dnsmasq conf

�ο����

�ű�
Shadowsocks + GfwList ʵ�� OpenWRT / LEDE ·�����Զ���ǽ
GFWlist+ShadowSocksʵ��·����͸������
shadowsock luci-app-shadowsocks GFWlist support
��¼��

�ο�����

С��·����3���¿���SSH�밲װShadowsocks������7��19�գ�
miwifi-ss
С��·����3 SSH + һ��SS �̳� ���������£�
ӡ��ʼ�:��������С��·����3��shadowsocks���ɹ��㶨��
�����С��·����������ʹ��shadowsocks
https://github.com/blademainer/miwifi-ss
https://github.com/boxcore/miwifi-ss/blob/master/r3_ss.sh
https://github.com/poodarchu/miwifi_ss/blob/master/miwifi.sh
[���鼼��] С��·����һ����װShadowsocks�̳�(֧��ȫ�ͺ�)
shadowsocks��CentOS7��С��·����mini�ϵ�Ӧ��
С��·������ο���Shadowsocks֧��
