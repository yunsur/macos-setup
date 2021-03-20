# Go

> Go 是一个开源的编程语言，它能让构造简单、可靠且高效的软件变得容易.

## 安装 Go

```bash
brew install go
```

## 配置 GOPATH

* 查看环境变量

```bash
go env
```

* 配置环境变量

`vim ~/.zshrc`

```vim
# go
export GO111MODULE=on
export GOPROXY=https://goproxy.cn
export GOBIN=$GOROOT/bin
export PATH=$PATH:$GOBIN
```

`source .zshrc`
