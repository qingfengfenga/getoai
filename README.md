# GetOAI

此存储库旨在通过整和开源工具，降低在本地运行生成式模型的复杂度，同时提高可用性。

## 概述

### 功能特性

- 使用 [New-API](https://github.com/Calcium-Ion/new-api) / [One-API](https://github.com/songquanpeng/one-api) 集中管理 Api、用户认证、额度管理等。

- 使用 [Dockge](https://github.com/louislam/dockge)、[Helm Dashboard](https://github.com/komodorio/helm-dashboard) 等可视化工具管理本地和远程工作负载。

- 使用 [Ollama](https://github.com/ollama/ollama)、[stable-diffusion-webui-docker](https://github.com/AbdBarho/stable-diffusion-webui-docker)、[midjourney-proxy](https://github.com/novicezk/midjourney-proxy) 等模型管理和 Api 代理工具。

- ChatUI 和模型 Api 服务，预置到 Dockge 中纳管，用户只需通过 WebUI 即可管理绝大部分服务，实现开箱即用。

### 兼容性

理论上 Windows、Linux、MacOS 都支持。

x86 和 ARM 也基本支持 

### 性能

Windows 下 Docker Desktop 容器性能损耗严重，尤其是大型模型加载期间。

如对性能有严格要求，建议使用 Linux 环境，将其添加为 Dockge 代理，即可通过 Dockge 管理。

或者使用非容器化方式运行，这不在仓库支持范围，但是依然可以使用提供的 New-api 管理 api 部分。

### 支持列表

#### 模型工具

| 支持     | 模型工具                       | New-api   | Dockge | Helm Dashboard |
|:--------:|:-----------------------------:|:---------:|:-------:|:-------------:|
|  ✔️     | Ollama                        |  ✔️       |  ✔️    |    ✖️        |
|  ✔️     | stable-diffusion-webui-docker |  ✔️       |  ✔️    |    ✖️        |
|  ✔️     | midjourney-proxy              |  ✔️       |  ✔️    |    ✖️        |

#### ChatUI

| 支持     | ChatUI                      | New-api   | Dockge  | Helm Dashboard |
|:--------:|:----------------------------:|:---------:|:-------:|:-------------:|
|  ✔️     | chatgpt-next-web             |  ✔️       |  ✔️     |    ✖️        |
|  ✔️     | chatgpt-web-midjourney-proxy |  ✔️       |  ✔️     |    ✖️        |
|  ✔️     | lobechat                     |  ✔️       |  ✔️     |    ✖️        |

## 开始使用

### 前提

- [Docker](https://docs.docker.com/get-docker/) 和 [Docker-compose](https://docs.docker.com/compose/)

- GPU（可以使用 CPU，但是会非常慢）

- 可访镜像仓库

- 可访问模型仓库，部分服务初始化会下载文件或模型

### 启动

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
OPT_STACKS_DIR=D:\getoai\volumes\dockge\opt\stacks
```

启动服务

```
docker-compose up -d
```

访问服务，设置管理员密码

- dockge：http://localhost:5001

- new-api：http://localhost:3000 （初始管理员 admin/admin）


可通过 Dockge 创建 模型和 ChatUI 工作负载，通过 New-api 管理Api。


## 鸣谢

- [New-API](https://github.com/Calcium-Ion/new-api) & [One-API](https://github.com/songquanpeng/one-api) 

- [Dockge](https://github.com/louislam/dockge)

- [Helm Dashboard](https://github.com/komodorio/helm-dashboard) 

- [Ollama](https://github.com/ollama/ollama)

- [stable-diffusion-webui-docker](https://github.com/AbdBarho/stable-diffusion-webui-docker)

- [midjourney-proxy](https://github.com/novicezk/midjourney-proxy) 

- [ChatGPT-Next-Web](https://github.com/ChatGPTNextWeb/ChatGPT-Next-Web)

- [chatgpt-web-midjourney-proxy](https://github.com/qingfengfenga/chatgpt-web-midjourney-proxy)

- [lobe-chat](https://github.com/lobehub/lobe-chat)

- [open-webui](https://github.com/open-webui/open-webui)

