https://blog.bluerain.io/p/udp-tunnel-0.html

https://www.jianshu.com/p/46d508f26def
https://evilmass.cc/2018/05/01/NS-%E5%8A%A0%E9%80%9F%E5%99%A8%E6%90%AD%E5%BB%BA-tinyfecVPN-udp2raw/

```
https://github.com/wangyu-/UDPspeeder/releases
https://github.com/wangyu-/udp2raw-tunnel/releases
https://github.com/wangyu-/udp2raw-multiplatform/wiki/%E5%BF%AB%E9%80%9F%E5%85%A5%E9%97%A8

https://github.com/Nyr/openvpn-install
https://build.openvpn.net/downloads/releases/
···

···
wget https://git.io/vpn -O openvpn-install.sh && bash openvpn-install.sh

nohup ./udp2raw_amd64 -s -l0.0.0.0:8855 -r 127.0.0.1:1194  -a -k "passwd" --raw-mode faketcp >/dev/null 2>&1 & 

服务端
nohup ./speederv2_amd64 -s -l0.0.0.0:8877 -r127.0.0.1:1194 --mode 0 -f2:4 -q1 >/dev/null 2>&1 &
nohup ./udp2raw_amd64 -s -l0.0.0.0:8855 -r 127.0.0.1:8877  -a -k "passwd" --raw-mode faketcp >/dev/null 2>&1 &

客户端
./udp2raw_arm -c -l0.0.0.0:2222 -r?.?.?.?:8855 -a -k "passwd" --raw-mode faketcp --cipher-mode xor
./speederv2_arm -c -l0.0.0.0:1111 -r127.0.0.1:2222 --mode 0 -f2:4 -q1

win客户端
# Run at client side
udp2raw_mp.exe -c -l0.0.0.0:3333  -r44.55.66.77:4096 -k "passwd" --raw-mode easy-faketcp


```

```
mssfix 1340
tun-mtu 1340

etc/openvpn/
*.conf
```
