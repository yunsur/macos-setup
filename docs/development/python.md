# Python

> Python 是一种解释型、面向对象、动态数据类型的高级程序设计语言.

## 安装 依赖

* 安装 zlib

```bash
brew install zlib
```

* 配置环境变量

`vim ~/.zshrc`

```vim
# zlib
export LDFLAGS="-L/usr/local/opt/zlib/lib"
export CPPFLAGS="-I/usr/local/opt/zlib/include"
export PKG_CONFIG_PATH="/usr/local/opt/zlib/lib/pkgconfig"
```

`source .zshrc`

## 安装 pyenv

```bash
brew install pyenv
```

* 配置环境变量

`vim ~/.zshrc`

```vim
# pyenv
eval "$(pyenv init -)"
```

`source .zshrc`

## pyenv 命令

* 查看远程 python 版本

```bash
pyenv install -l
```

* 查看本机 python 版本

```bash
pyenv versions
```

* 安装其他 python 版本

```bash
pyenv install 2.7.18
```

* 卸载其他 python 版本

```bash
pyenv uninstall 2.7.18
```

## 创建独立 Python 虚拟环境

* 回到用户目录

```bash
cd ~
```

* 本地激活

```bash
pyenv local 2.7.18
```

```bash
# 检查版本 Python 2.7.18
python --version
```

## 安装 虚拟环境 管理工具

```bash
pip install virtualenvwrapper
```

* 配置环境变量

`vim ~/.zshrc`

```bash
# virtualenv
export WORKON_HOME=$HOME/.virtualenvs
export PROJECT_HOME=$HOME/Sources
source $HOME/.pyenv/versions/3.9.1/bin/virtualenvwrapper.sh
```

`source .zshrc`

## virtualenvwrapper 命令

* 查看创建的虚拟环境

```bash
lsvirtualenv
# 或者
$ workon
```

* 创建并激活新环境

```bash
mkvirtualenv env27
```

* 激活 env27 虚拟环境

```bash
workon env27
```

* 退出 env27 虚拟环境

```bash
deactivate
```

* 删除 env27 虚拟环境

```bash
rmvirtualenv env27
```

## 遍历移除项目中的所有 .pyc 文件

```bash
find ./ -name "*.pyc" | xargs rm -rf
```