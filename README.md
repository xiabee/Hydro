# Hydro

## 版本说明

* 更新`docker-compose`



## 开源许可

本项目基于 AGPL-3.0-or-later 开源。  
在您部署 Hydro 时，需要保留底部的 `Powered by Hydro` 字样，其中的 `Hydro` 字样需指向 `hydro.js.org/本仓库/fork` 之一的链接。  
若您对源码做出修改/扩展，同样需要以 AGPL-3.0-or-later 开源，您可以以 `Powered by Hydro, Modified by xxx` 格式在页脚注明。  

## 注意

安装过程中，会默认注册一个超级管理员账号，用来做测评账号。用户名：`root`，密码：`rootroot`。**请务必及时修改密码**。修改该账号密码后，请修改`data/judge/config/judge.yaml`中的`password`。否则可能会无法测评。

## 

## 测评机默认编译器

测评机默认安装了以下几个编译器，如有需要，请自行安装。

编译器列表：

```- bash
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
