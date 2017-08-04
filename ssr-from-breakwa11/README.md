Dockerfile from braakwa11（原项目已经删除，这里做了部分修改），本Dockerfile参数更具可定制性，使用步骤如下：

```
docker build -t=ssr0 .
```

```
docker run -p 55349:55349 --restart=always --name ssr0 ssr0
```
Or
```
docker run -p 55349:55349 --restart=always --name ssr0 -e PASSWORD="change_your_pwd" -e METHOD="chacha20" -e PROTOCOL="origin" -e OBFS="tls1.2_ticket_auth" ssr0
```

默认以及可定制参数如下：
```
ENV PASSWORD        change_your_pwd
ENV METHOD          aes-128-ctr
ENV PROTOCOL        auth_aes128_md5
ENV PROTOCOLPARAM   32
ENV OBFS            tls1.2_ticket_auth_compatible
```



