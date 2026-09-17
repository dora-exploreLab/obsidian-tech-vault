---
title: "{{title}}"
created: "{{date}}"
server: 阿里云 ECS
target: 本地 Windows 台式机
tags:
  - devops
  - reverse-proxy
  - network
---

# 🖥️ 运维方案/网络穿透：{{title}}

## 🌐 网络拓扑与端口映射
- **公网跳板机 (阿里云 ECS)**：IP: `公网IP`, 开放端口: `SSH (如 60022) / RDP (如 63389)`
- **目标机器 (本地台式机)**：内网 IP, 本地端口: `22 (SSH) / 3389 (RDP)`
- **穿透技术方案**：(FRP / SSH Tunnel / Cloudflare Tunnels / NPS)

## ⚙️ 核心配置文件记录

### 1. 服务端配置 (阿里云 ECS)
```ini
# 服务端配置文件路径 (如 /etc/frp/frps.toml)
bindPort = 7000
auth.token = "YOUR_SECURE_TOKEN"
```

### 2. 客户端配置 (本地台式机)
```ini
# 客户端配置文件路径
serverAddr = "x.x.x.x"
serverPort = 7000
auth.token = "YOUR_SECURE_TOKEN"

[[proxies]]
name = "desktop-ssh"
type = "tcp"
localIP = "127.0.0.1"
localPort = 22
remotePort = 60022

[[proxies]]
name = "desktop-rdp"
type = "tcp"
localIP = "127.0.0.1"
localPort = 3389
remotePort = 63389
```

## 🛠️ 自启动与健康检查
- **守护进程**：`systemctl status frps` / Windows `NSSM` 服务
- **连通性测试命令**：
  ```bash
  ssh -p 60022 user@ECS_PUBLIC_IP
  mstsc /v:ECS_PUBLIC_IP:63389
  ```

## ⚠️ 安全防护规则
- [ ] 阿里云安全组白名单限制（仅允许特定 IP 或高位非常规端口）
- [ ] 禁用 SSH 密码登录，强制启用 SSH 密钥对
- [ ] Windows 防火墙策略与复杂账户密码
