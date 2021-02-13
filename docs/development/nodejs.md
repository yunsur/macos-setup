# Node.js

> Node.js 是一个事件驱动I/O服务端 JavaScript 环境，基于 Google 的 V8 引擎，V8 引擎执行 Javascript 的速度非常快，性能非常好。

nvm，node，npm，nrm 之间的区别

* nvm：nodejs 版本管理工具

* nodejs：在项目开发时的所需要的代码库

* npm：nodejs 包管理工具

* nrm: npm 镜像源管理工具

## nvm 安装

* 安装 nvm

```bash
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.35.2/install.sh | bash
```

* 配置环境变量

`vim ~/.zshrc`

```bash
# nvm
export NVM_DIR="$HOME/.nvm"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"  # This loads nvm
[ -s "$NVM_DIR/bash_completion" ] && \. "$NVM_DIR/bash_completion"  # This loads nvm bash_completion
```

`source .zshrc`

## nvm 命令

```bash
nvm install stable                ## 安装最新稳定版 
nvm install <version>             ## 安装指定版本 
nvm uninstall <version>           ## 删除已安装的指定版本 
nvm use <version>                 ## 切换使用指定的版本
nvm ls                            ## 列出所有安装的版本 
nvm ls-remote                     ## 列出所有远程服务器的版本 
nvm current                       ## 显示当前的版本 
nvm alias <name> <version>        ## 给不同的版本号添加别名 
nvm unalias <name>                ## 删除已定义的别名 
nvm reinstall-packages <version>  ## 在当前版本 node 环境下，重新全局安装指定版本号的 npm 包 
nvm alias default [node版本号]    ##设置默认版本
```

## npm 全局使用

* 需要手动修改 npm 默认目录(具有读写权限的目录)，进行创建全局目录

```bash
mkdir ~/.nvm/.npm-global
```

* 配置 npm 新路径

```bash
npm config set prefix '~/.nvm/.npm-global'
```

* 配置环境变量

`vim ~/.zshrc`

```vim
export PATH=$HOME/.nvm/.npm-global/bin:$PATH
```

`source .zshrc`

* 重新打开终端输入

```bash
npm i -g npm
```

## nrm 安装和使用

* nrm 安装

```bash
npm i -g nrm
```

* 列出可用的源

```bash
nrm ls
```

* 淘宝源

```bash
nrm use taobao
```