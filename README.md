<div align="center">

<img width="160" src="https://raw.githubusercontent.com/perfect-panel/ppanel-assets/refs/heads/main/logo.svg">

<h1>PPanel Quick Deployment Guide</h1>

This is a quick deployment script provided by PPanel

English · [中文](./README.zh-CN.md)

</div>

## Install Docker

First, run the following command to install Docker:

```sh
curl -fsSL https://get.docker.com | bash -s docker
```

## Clone Git Repository

Next, clone the project's Git repository:

```sh
git clone https://github.com/perfect-panel/ppanel-script.git
cd ppanel-script
```

## Start Deployment

**Before deployment, modify the configuration files to suit your actual deployment needs and ensure the configurations are correct.**

The application includes a default administrator account for initial setup:

- **Username**: `admin@ppanel.dev`
- **Password**: `admin-password`

> **Note**: Change the default password after the first login to ensure security.

### One-Click Deployment

Run the following command to deploy PPanel with one click:

```sh
 docker compose up -d
```

### Deploy the Server Side

[Configuration File Instructions](https://docs.ppanel.dev/en-US/docs/server#modify-configuration-file)

If you only need to deploy the server side, run the following command:

```sh
 docker compose -f ppanel-server.yml up -d
```

### Deploy the Admin Panel

[Environment Variables Instructions](https://docs.ppanel.dev/en-US/docs/admin#environment-variables)

If you need to deploy the admin panel, run the following command:

```sh
 docker compose -f ppanel-admin-web.yml up -d
```

### Deploy the User Panel

[Environment Variables Instructions](https://docs.ppanel.dev/en-US/docs/user#environment-variables)

If you need to deploy the user panel, run the following command:

```sh
 docker compose -f ppanel-user-web.yml up -d
```

### Deploy the Frontend

If you need to deploy both the admin panel and the user panel, run the following command:

```sh
 docker compose -f ppanel-web.yml up -d
```

## Post-Deployment Operations

After deployment, to ensure the service is running properly, you can check the running status using the following command:

```sh
 docker compose ps
```

If you need to restart the service, run the following command:

```sh
 docker compose restart
```

If an error occurs, you can check the error logs with the following command:

```sh
 docker compose logs -f
```

