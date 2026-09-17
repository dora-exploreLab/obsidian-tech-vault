---
title: "现代全栈开发者与 Docker 极客速查手册"
type: "cheatsheet"
category: "devops"
updated: 2026-09-17
tags:
  - reference
  - cheatsheet
  - docker
  - devops
---

# 🧰 示例：现代全栈开发者与 Docker 极客速查手册

> 💡 **范例说明**：本文件为 `07 - 手册资料` 的速查字典样本，践行**“认知卸载（Cognitive Offloading）”**原则——把琐碎的命令参数移出生物大脑内存，随查随用。

---

## 🐳 一、Docker 容器与镜像高频神级指令

### 1. 容器深度排障与实时指标
```bash
# 实时查看全量容器 CPU、内存、网络 I/O 占用 (高阶带格式)
docker stats --format "table {{.Name}}\t{{.CPUPerc}}\t{{.MemUsage}}\t{{.NetIO}}"

# 极速进入容器内并启用 bash/sh 调试
docker exec -it <container_name_or_id> /bin/sh

# 查看容器最近 200 行实时带时间戳日志并持续跟踪
docker logs -f --tail 200 -t <container_name>
```

### 2. 存储卷与孤儿垃圾一键深度清洗
```bash
# 彻底清理所有已停止容器、未悬空悬空网络及无用缓存（释放几十G磁盘神技）
docker system prune -a --volumes -f
```

---

## 🚀 二、生产级 Docker Compose 模板速查

```yaml
version: '3.8'

services:
  app-backend:
    image: node:20-alpine
    restart: unless-stopped
    ports:
      - "3000:3000"
    environment:
      - NODE_ENV=production
      - DATABASE_URL=postgresql://user:pass@postgres-db:5432/main_db
    depends_on:
      postgres-db:
        condition: service_healthy

  postgres-db:
    image: postgres:16-alpine
    restart: always
    volumes:
      - pg_data:/var/lib/postgresql/data
    healthcheck:
      test: ["CMD-SHELL", "pg_isready -U user -d main_db"]
      interval: 5s
      timeout: 5s
      retries: 5

volumes:
  pg_data:
```
