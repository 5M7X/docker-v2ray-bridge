# docker配置的v2ray服务端与客户端

## 背景
自用于将家中内外通过 `v2ray` 加密代理进行访问浏览服务。

同时也是标准的 `v2ray` 服务端和客户端的实现。

## 结构
服务端使用 `caddy` 进行代理 `v2ray` websocket 的服务。
客户端与 `docker` 代理出来的端口相连。


## 使用

需申请一个证书用来 TLS ， 如果你不需要加密，那就改一下配置。相关配置在 v2ray 和 caddy 中都可以找到。

此处 v2ray 暴露的端口在 caddyfile 中写明，docker-compose.yml 中的端口与内网穿透服务的端口一致。

客户端的端口则是网络出口，即内网穿透出来的端口/光猫暴露的对外端口。

如此，在服务端上起 server ：docker-compose up -d

在客户端上起 client ： docker-compose up -d

没有意外的话，连接就 ok 了。

