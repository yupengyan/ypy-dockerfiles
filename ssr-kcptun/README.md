脚本经过测试可行能用，安装步骤：

1. Build
```
docker build -t=ssr-kcptun .

```

2. Run
```
docker run -p 80:80 -p 4000:4000 --restart=always --name ssr-kcptun ssr-kcptun

```

Dockerfile默认利用start.sh中的定义，所以上面docker进行80与4000端口映射：
```
#!/bin/bash
python  /shadowsocksr/shadowsocks/server.py -p 80 -k ij0LevE6XvuiKeTyGIET -m chacha20 -o tls1.2_ticket_auth_compatible -O auth_sha1_v4_compatible -d start
sleep 5
./server_linux_amd64 -t "127.0.0.1:80" -l ":4000" -mode fast2
```