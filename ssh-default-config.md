---
title: SSH 客户端的默认配置文件
published: 2025-05-02T08:00:00
modified: 2025-07-13T23:54:11
tags:
  - ssh
---

SSH 客户端配置文件 `~/.ssh/config`

使用通配符匹配所有主机：

```
Host *
    IdentityFile ~/.ssh/id_ed25519
    ServerAliveInterval 15
    ServerAliveCountMax 10
```

- `IdentityFile` 指定用于身份验证的私钥文件路径。
- `ServerAliveInterval` 每 15 秒客户端会向服务器发送一个信号，以确保连接不会因为长时间无活动而断开。
- `ServerAliveCountMax` 如果在 10 次尝试后服务器仍未响应，客户端会终止连接。

采用 SSH 客户端保活，而不是服务端保活，配置起来简单一点。
