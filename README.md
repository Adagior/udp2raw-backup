https://blog.bluerain.io/p/udp-tunnel-0.html

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

```

```
mssfix 1340
tun-mtu 1340

etc/openvpn/
*.conf
```
