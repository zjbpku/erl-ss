link to: https://github.com/leontius/shadowsocks_erlite3
link to: https://github.com/ld0891/ubnt-shadowsocks-libev

��װ(ex: goole search below files, erl: install *mips.deb files )
sudo dpkg -i apg_2.2.3.dfsg.1-2_mipsel.deb
sudo dpkg -i pwgen_2.07-1_mipsel.deb
sudo dpkg -i libc6_2.19-18+deb8u7_mipsel.deb
sudo dpkg -i libev4_4.15-3_mipsel.deb
sudo dpkg -i libmbedcrypto0_2.4.0-1-bpo8+1_mipsel.deb
sudo dpkg -i libpcre3_8.35-3.3+deb8u4_mipsel.deb
sudo dpkg -i libsodium18_1.0.11-1-bpo8+1_mipsel.deb
sudo dpkg -i libudns0_0.4-1_mipsel.deb
sudo dpkg -i shadowsocks-libev_3.0.5-1_mipsel.deb

��װ: 1.����shadowsocks_erlite3-xxxx.zip����ѹ
2.��winscp�ѽ�ѹ�������ļ�copy��/tmpĿ¼
3.����·��CLI������沢��½��Ȼ��ִ��:
cd /tmp
sudo bash install.sh
4.������ʾ����shadowsocks������Ϣ��һ��ֻ��Ҫ�����������ַ���˿ڡ����룬����ѡ�����ֱ�ӻس�ʹ��Ĭ��ѡ�

ע��: 1.�����������Զ�������ͨ��ipset�Թ���IP���а�����������IP���ᷭǽ���ʣ�ֻ�й�����������shadowsocksͨ����ǽ
2.ֻ�ܶ�TCP������ǽ
3.������վDNS��shadowsocks��������תʹ��TCP����8.8.8.8����ֹ��Ⱦ����������ʹ�ù���DNS����������Ӱ��CDN����
4.1080�˿ڿ�����Ϊsocks5��ǽ����ʹ��
5.�ļ������/configĿ¼����Ϊ���Ŀ¼�������õ�ʱ��ᱻһ�𱸷ݣ�����ϵͳ����Ҳ����ɾ��
6.shadowsocks-libev�汾:v3.1.0, chinadns�汾:v1.3.2(�޸İ�)��pdnsd�汾:v1.2.9
7.EdgeRouter X EdgeOS v1.8.5,v1.9.0����ͨ��
8.�������ͣshadowsocks������sudo /etc/init.d/shadowsocks stop
9.��������������sudo /etc/init.d/shadowsocks start
10.����sudo crontab -e�������ļ�ĩβ����������ݣ��Ϳ���ʵ��ÿ��5���Ӽ��ss״̬��������ܷ�ǽ���Զ���������
*/5 * * * * sh /config/shadowsocks/bin/ss-monitor.sh

PT�����û���ע�⣬������ж��������ػ����������������ػ�����SS������������£�
ss�����ű�/etc/init.d/shadowsocks����������һ��:
#BYPASS_RANGE=192.168.123.0/24
ȥ��ע��(ɾ��#��)��������Ϳ�����Ч��Ȼ��192.168.123.0/24���������ζ�������ssͨ���ˣ�ͬʱҲ�޷���ǽ�ˣ�192.168.123.0/24Ҳ���Ի��ɵ���IP�����������Ρ�

DNS��������
chinadns ������������һ������DNS��һ������DNS
dnsmasq -> chinadns (����IP)-> pdnsd -> ss-server -> dns-server:ok
(����IP)-> 114.114.114.114:ok

chinadns���ߺܾ�û�и��¹��ˣ������м���bug���ᵼ����Щͬʱ�й��ڹ���CDN�����������������IP��������ʹ�õ�chinadns���޸������bug���Ż��˲�������µĽ����ٶȡ�
ss��ǽ����Ŀǰ�����׳�����ľ���DNS����Ⱦ������ļ��θ��¼����������DNS����Ŀǰ�汾�������ұȽ������ˡ�