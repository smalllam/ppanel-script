<div align="center">

<img width="160" src="https://raw.githubusercontent.com/perfect-panel/ppanel-assets/refs/heads/main/logo.svg">

<h1>PPanel 快速部署指南</h1>

这是由 PPanel 提供支持的快速部署脚本

[英文](./README.md) · 中文

</div>

## 安装 Docker

首先运行以下命令安装 Docker：

```sh
curl -fsSL https://get.docker.com | bash -s docker
```

## 克隆 Git 仓库

接下来，克隆项目的 Git 仓库：

```sh
git clone https://github.com/perfect-panel/ppanel-script.git
cd ppanel-script
```

## 开始部署

**部署前，请修改配置文件以适应您的实际部署需求，确保配置正确无误**

应用程序包含一个用于初始设置的默认管理员账户：

- **用户名**：`admin@ppanel.dev`
- **密码**：`admin-password`

> **注意**：首次登录后请更改默认密码以确保安全。

### 一键部署

运行以下命令一键部署 PPanel：

```sh
 docker compose up -d
```

### 部署服务端

[配置文件说明](https://docs.ppanel.dev/zh-CN/docs/server#%E4%BF%AE%E6%94%B9%E9%85%8D%E7%BD%AE%E6%96%87%E4%BB%B6)

如果只需要部署服务端，运行以下命令：

```sh
 docker compose -f ppanel-server.yml up -d
```

### 部署管理端

[环境变量说明](https://docs.ppanel.dev/zh-CN/docs/admin#%E7%8E%AF%E5%A2%83%E5%8F%98%E9%87%8F)

如果需要部署管理端，运行以下命令：

```sh
 docker compose -f ppanel-admin-web.yml up -d
```

### 部署用户端

[环境变量说明](https://docs.ppanel.dev/zh-CN/docs/user#%E7%8E%AF%E5%A2%83%E5%8F%98%E9%87%8F)

如果需要部署用户端，运行以下命令：

```sh
 docker compose -f ppanel-user-web.yml up -d
```

### 部署前端

如果需要同时部署管理端和用户端，运行以下命令：

```sh
 docker compose -f ppanel-web.yml up -d
```

## 部署后的运行事项

部署完成后，为确保服务正常运行，可以使用以下命令查看运行状态：

```sh
 docker compose ps
```

如果需要重新启动服务，可以运行以下命令：

```sh
 docker compose restart
```

当服务发生错误时，可以使用以下命令查看错误日志：

```sh
 docker compose logs -f
```


