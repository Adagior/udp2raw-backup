https://blog.bluerain.io/p/udp-tunnel-0.html

https://www.jianshu.com/p/46d508f26def

https://evilmass.cc/2018/05/01/NS-%E5%8A%A0%E9%80%9F%E5%99%A8%E6%90%AD%E5%BB%BA-tinyfecVPN-udp2raw/

https://www.moerats.com/archives/662/

```
https://github.com/wangyu-/UDPspeeder/releases
https://github.com/wangyu-/udp2raw-tunnel/releases
https://github.com/wangyu-/tinyPortMapper/releases
https://github.com/wangyu-/udp2raw-multiplatform/wiki/%E5%BF%AB%E9%80%9F%E5%85%A5%E9%97%A8

https://github.com/Nyr/openvpn-install
https://build.openvpn.net/downloads/releases/

···

···
wget https://github.com/Adagior/udp2raw-backup/raw/master/2.zip
yum install -y unzip zip
unzip 2.zip
chmod a+x speederv2_amd64
chmod a+x udp2raw_amd64
tar -zxvf udp2raw_binaries.tar.gz
tar -zxvf speederv2_binaries.tar.gz

wget https://git.io/vpn -O openvpn-install.sh && bash openvpn-install.sh

cd /etc/openvpn/server/
wget https://github.com/Adagior/udp2raw-backup/raw/master/server.conf

firewall-cmd --direct --add-rule ipv4 nat POSTROUTING 0 -s 10.8.0.0/24 ! -d 10.8.0.0/24 -j SNAT --to ?.?.?.?
firewall-cmd --permanent --direct --add-rule ipv4 nat POSTROUTING 0 -s 10.8.0.0/24 ! -d 10.8.0.0/24 -j SNAT --to ?.?.?.?


服务端
nohup ./speederv2_amd64 -s -l0.0.0.0:18899 -r127.0.0.1:11111 --mode 0 -f2:4 -q1 >/dev/null 2>&1 &
nohup ./udp2raw_amd64 -s -l0.0.0.0:18877 -r 127.0.0.1:18899  -a -k "passwd" --raw-mode faketcp --cipher-mode xor >/dev/null 2>&1 &

客户端
nohup ./udp2raw_amd64 -c -l0.0.0.0:2222 -r?.?.?.?:8877 -a -k "passwd" --raw-mode faketcp --cipher-mode xor >/dev/null 2>&1 &
nohup ./speederv2_amd64 -c -l0.0.0.0:1212 -r127.0.0.1:2222 --mode 0 -f2:4 -q1 >/dev/null 2>&1 &

win客户端
# Run at client side
udp2raw_mp.exe -c -l0.0.0.0:3333  -r44.55.66.77:4096 -k "passwd" --raw-mode easy-faketcp

bat命令
@echo off  
start cmd /k C:\Users\legend_ko\Desktop\VPN\zzz\speederv2.exe -c -l0.0.0.0:1111 -r127.0.0.1:2222 --mode 0 -f2:4 -q1
start cmd /k C:\Users\legend_ko\Desktop\VPN\zzz\udp2raw_mp_nolibnet.exe -c -l0.0.0.0:2222 -r?.?.?.?:8877 -k "passwd" --raw-mode faketcp


```

```
mssfix 1340
tun-mtu 1340

etc/openvpn/
*.conf
```

路由
https://github.com/FQrabbit/VPN-skip-China-route-Window 
