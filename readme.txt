link to: https://github.com/leontius/shadowsocks_erlite3
link to: https://github.com/ld0891/ubnt-shadowsocks-libev

安装(ex: goole search below files, erl: install *mips.deb files )
sudo dpkg -i apg_2.2.3.dfsg.1-2_mipsel.deb
sudo dpkg -i pwgen_2.07-1_mipsel.deb
sudo dpkg -i libc6_2.19-18+deb8u7_mipsel.deb
sudo dpkg -i libev4_4.15-3_mipsel.deb
sudo dpkg -i libmbedcrypto0_2.4.0-1-bpo8+1_mipsel.deb
sudo dpkg -i libpcre3_8.35-3.3+deb8u4_mipsel.deb
sudo dpkg -i libsodium18_1.0.11-1-bpo8+1_mipsel.deb
sudo dpkg -i libudns0_0.4-1_mipsel.deb
sudo dpkg -i shadowsocks-libev_3.0.5-1_mipsel.deb



安装:
0.下载后 erl 上可以直接用install_dpkg.sh安装；ex上需下载 *mipsel.deb文件
1.下载shadowsocks_erlite3-xxxx.zip并解压  从这https://github.com/ld0891/ubnt-shadowsocks-libev release下载最新版本
2.用winscp把解压的所有文件copy到/tmp目录
3.连接路由CLI命令界面并登陆，然后执行:
cd /tmp
sudo bash install.sh
4.根据提示输入shadowsocks配置信息，一般只需要输入服务器地址、端口、密码，其它选项可以直接回车使用默认选项。
5.如果想暂停shadowsocks，运行sudo /etc/init.d/shadowsocks stop
6.重新启动就运行sudo /etc/init.d/shadowsocks start
7.运行sudo crontab -e，并在文件末尾添加以下内容，就可以实现每隔5分钟检测ss状态，如果不能翻墙就自动重启服务：
*/5 * * * * sh /config/shadowsocks/bin/ss-monitor.sh

完美
