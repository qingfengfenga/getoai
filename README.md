# GetOAI

此存储库旨在通过整和开源工具，降低在本地运行生成式模型的复杂度和可用性。

## 概述

使用 New-Api / One-Api 集中管理 Api、用户认证、额度管理等

使用 Dockge、Helm Dashboard 等可视化工具管理本地和远程工作负载

ChatUI 和模型 Api 服务，预置到 Dockge 中纳管，用户只需通过 WebUI 即可管理绝大部分服务，实现开箱即用。

## 开始

克隆本存储库，克隆完成后，进入文件夹

```
cd getoai
```
复制一份配置文件

```
cp .env.example .env
```
修改 .env 文件
```
# ⚠️ Stacks directory (MUST) 
# FULL path only. No relative path (MUST)
# Git_DIR + volumes\dockge\opt\stacks
# eg: D:\getoai\volumes\dockge\opt\stacks
OPT_STACKS_DIR=D:\Me\getoai\volumes\dockge\opt\stacks
```

启动服务

```
docker-compose up -d
```

访问服务

dockge
http://localhost:5001

new-api
http://localhost:3000

分别设置密码

可通过 dockge 创建工作负载