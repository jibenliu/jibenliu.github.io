+++
title = "环境安装"
description = "golang learning"
date = "2022-05-27"
aliases = ["golang", "go"]
author = "Hugo Authors"
tags = [
"shortcodes"
]
+++

## 安装

### 基础安装
```shell
sudo apt install golang
```
### gvm多版本管理
```shell
// gvm 安装
bash < <(curl -s -S -L https://raw.githubusercontent.com/moovweb/gvm/master/binscripts/gvm-installer)

// gvm 组件依赖bison安装
sudo apt install bison

// gvm安装指定版本
gvm install go1.18

// 切换到指定版本
gvm use go1.18

// 切换后设置为环境变量
gvm use go1.18 --default
```

### 设置中国镜像
```shell
go env -w export GOPROXY=https://goproxy.io
或者
go env -w export GOPROXY=https://goproxy.cn
```

### 关闭sum校验
```shell
go env -w GOSUMDB=off
```

### 设置私有代理
```shell
go env -w GOPRIVATE=*.gitlab.com,*.gitee.com
```

### 初始化项目
```shell
mkdir demo

cd demo

go mod init demo

// 添加import包
// ....
// 业务代码 

go mod tidy
go mod vendor
```

遇到go mod 无法安装的可以通过以下办法安装
```shell
cd demo/vendor/github.com/golang

git clone https://github.com/golang/sync.git
git clone https://github.com/golang/crypto.git
git clone https://github.com/golang/sys.git
```