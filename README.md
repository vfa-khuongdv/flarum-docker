# mondedie/flarum

![logo](https://i.imgur.com/Bjrtbsc.png)

[![](https://github.com/mondediefr/docker-flarum/workflows/build/badge.svg)](https://github.com/mondediefr/docker-flarum/actions)
[![](https://img.shields.io/docker/pulls/mondedie/flarum)](https://hub.docker.com/r/mondedie/flarum)
[![](https://img.shields.io/docker/stars/mondedie/flarum)](https://hub.docker.com/r/mondedie/flarum)

### Features

- Multi-platform image: `linux/386`, `linux/amd64`, `linux/arm/v6`, `linux/arm/v7`, `linux/arm64`
- Lightweight & secure image
- Based on Alpine Linux 3.16
- **nginx** and **PHP 8.0**
- Latest [Flarum Framework](https://github.com/flarum/framework) (v1.3.0)
- MySQL/Mariadb driver
- OPCache extension configured

### Build-time variables

- **VERSION** = Version of [flarum/flarum](https://github.com/flarum/flarum) skeleton (default: *v1.3.0*)

### Ports

- Default: **8888** (configurable)

### Volume

- **/flarum/app/extensions** : Flarum extension directory
- **/flarum/app/public/assets** : Flarum assets directory
- **/flarum/app/storage/logs** : Flarum logs directory
- **/etc/nginx/flarum** : Nginx location directory

### Environment variables

| Variable | Description                                 | Type | Default value |
| -------- |---------------------------------------------| ---- | ------------- |
| **UID** | Flarum user id                              | *optional* | 991
| **GID** | Flarum group id                             | *optional* | 991
| **DEBUG** | Flarum debug mode                           | *optional* | false
| **FORUM_URL** | Forum URL                                   | **required** | none
| **DB_HOST** | MySQL instance ip/hostname                  | *required* | mariadb
| **DB_USER** | MySQL database username                   | *required* | flarum
| **DB_NAME** | MySQL database name                       | *required* | flarum
| **DB_PASS** | MySQL database password                   | **required** | none
| **DB_PORT** | MySQL database port                       | *required* | 3306
| **DB_PREF** | Flarum tables prefix                        | *optional* | none
| **FLARUM_PORT** | Port to run Flarum on inside the container  | *optional* | 8888
| **UPLOAD_MAX_SIZE** | The maximum size of an uploaded file        | *optional* | 50M
| **PHP_MEMORY_LIMIT** | PHP memory limit                            | *optional* | 128M |
| **OPCACHE_MEMORY_LIMIT** | OPcache memory size in megabytes            | *optional* | 128
| **LOG_TO_STDOUT** | Enable nginx and php error logs to stdout   | *optional* | false
| **GITHUB_TOKEN_AUTH** | Github token to download private extensions | *optional* | false
| **PHP_EXTENSIONS** | Install additional php extensions           | *optional* | none

### Required environment variable for first installation

| Variable | Description | Type | Default value |
| -------- | ----------- | ---- | ------------- |
| **FLARUM_ADMIN_USER** | Name of your user admin | **required** | none
| **FLARUM_ADMIN_PASS** | User admin password | **required** | none
| **FLARUM_ADMIN_MAIL** | User admin adress mail | **required** | none
| **FLARUM_TITLE** | Set a name of your flarum | *optional* | Docker-Flarum

## Installation

#### 1 - Start docker form localhost

```bash
docker compose up -d
```

#### 2 - Visit forum
Forum: http://localhost

## License

Docker image [mondedie/flarum](https://hub.docker.com/r/mondedie/flarum) is released under [MIT License](https://github.com/mondediefr/docker-flarum/blob/master/LICENSE).
