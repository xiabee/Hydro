# Hydro-Docker

## 版本说明

* `Docker`一键式搭建`Hydro-OJ`测评系统

* Powered by [Hydro](https://github.com/hydro-dev/Hydro), Modified by [xiabee](https://github.com/xiabee/Hydro-Docker)

### 

## 使用方式

```bash
docker-compose up -d
# 若未产生报错则运行成功
```

* 注意：本项目在本地编译镜像，使用清华源，若海外服务器无法访问清华源可以修改`./backend/Dockerfile`和`./judge/Dockerfile`中的`3~5`行：
  
  ```dockerfile
  RUN sed -i "s/deb.debian.org/mirrors.tuna.tsinghua.edu.cn/g" /etc/apt/sources.list && \
      sed -i "s/security.debian.org/mirrors.tuna.tsinghua.edu.cn/g" /etc/apt/sources.list && \
      apt-get update && apt-get install -y --no-install-recommends && apt upgrade -y
  ```

## 测评机默认编译器

```-
- gcc
- python3
- g++
- fp-compiler
- openjdk-8-jdk-headless
- python
- php7.0-cli
- rustc
- haskell-platform
- libjavascriptcoregtk-4.0-bin
- golang
- ruby
- mono-runtime
- mono-mcs
```

## 注意

修改该账号密码后，请修改`data/judge/config/judge.yaml`中的`password`。否则可能会无法测评。

## Docker相关

```bash
docker-compose up -d
# 创建并后台运行容器
docker-compose start
# 开启容器
docker-compose stop
# 关闭容器
docker-compose restart
# 重启容器
docker-compose down
# 删除容器
```

* `docker`入门教程参考这里：[Docker入门 · xiabee-瞎哔哔](https://blog.xiabee.cn/posts/docker-pupy/)
