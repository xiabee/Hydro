# Hydro

## 版本说明

* 更新`docker-compose`



### 使用方式

```bash
docker-compose up -d
```

## 

## 注意

安装过程中，会默认注册一个超级管理员账号，用来做测评账号。用户名：`root`，密码：`rootroot`。**请务必及时修改密码**。

修改该账号密码后，请修改`data/judge/config/judge.yaml`中的`password`。否则可能会无法测评。

## 

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
