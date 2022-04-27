# Hydro-Docker

## 版本说明

* `Docker`一键式搭建`Hydro-OJ`测评系统

* Powered by [Hydro](https://github.com/hydro-dev/Hydro), Modified by [xiabee](https://github.com/xiabee/Hydro-Docker)

### 

## 搭建方式

```bash
docker-compose up -d
# 若未产生报错则运行成功
```

* 注意：本项目在本地编译镜像，使用清华源，若海外服务器无法访问清华源可以修改`./backend/Dockerfile`和`./judge/Dockerfile`中的`3~5`行，将其换为对应的源即可：
  
  ```dockerfile
  RUN sed -i "s/deb.debian.org/mirrors.tuna.tsinghua.edu.cn/g" /etc/apt/sources.list && \
      sed -i "s/security.debian.org/mirrors.tuna.tsinghua.edu.cn/g" /etc/apt/sources.list && \
      apt-get update && apt-get install -y --no-install-recommends && apt upgrade -y
  ```



## 配置管理员账号

* 右上角注册新账号

* 在刚刚运行`docker-compose`目录的目录下执行以下命令，设置超级管理员：
  
  ```bash
  docker exec oj-backend -it hydrooj cli user setSuperAdmin 2
  # 将UID为2的用户设置为管理员
  docker exec oj-backend -it pm2 restart hydrooj
  # 重新启动hydro
  ```



## 配置测评机

* 测评机需要管理员账号

* 修改宿主机中的`./data/judge/judge.yaml`，将`uname`和`password`修改为对应管理员账号的用户名和密码：
  
  ```yaml
  hosts:
    localhost:
      type: hydro
      server_url: http://oj-backend:8888/
      uname: root
      password: rootroot
      detail: true
  ```

* 重启容器：
  
  ```bash
  docker-compose restart
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
