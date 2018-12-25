https://blog.bluerain.io/p/udp-tunnel-0.html

nohup command >/dev/null 2>&1 & ./udp2raw_amd64 -s -l0.0.0.0:8855 -r 127.0.0.1:1194  -a -k "passwd" --raw-mode faketcp

