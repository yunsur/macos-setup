# Homebrew

> [Homebrew](https://brew.sh) 包管理工具可以让你安装和更新程序变得更方便，目前在 OS X 系统中最受欢迎的包管理工具是 Homebrew.

## 安装 Homebrew

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

## Homebrew 用法

* 搜索

```bash
brew search <formula>
```

* 安装

```bash
brew install <formula>
```

* 更新

```bash
brew update
```

* 升级

```bash
brew upgrade <formula>
```

* 显示可以升级的包

```bash
brew outdated
```

* 完成安装后可以列出已安装内容

```bash
brew list
```

* 信息

```bash
brew info <formula>
```

* 清理

```bash
brew cleanup
```

* 卸载

```bash
brew uninstall <formula>
```
