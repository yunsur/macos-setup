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
export GOPATH=$HOME/go
export GOBIN=$GOPATH/bin
export PATH=$PATH:$GOBIN
```

`source .zshrc`

## 变量说明

```
GOROOT：安装目录（go语言安装目录）。
GOPATH：工程目录（自己工程项目目录）。
GOBIN：可执行文件目录。
PATH：将go可执行文件加入PATH中，使GO命令与我们编写的GO应用可以全局调用。
GOPATH包含三个目录：bin、pkg、src。
src目录：源文件。
pkg目录：编译好的库文件，主要是*.a文件。
bin目录：可执行文件。

注意：千万不要把GOPATH设置成go的安装路径。
```