# 终端配置

## iTerm2

> iTerm2 是默认终端的替代品，也是目前 Mac 系统下最好用的终端工具，集颜值和效率于一身。

* 安装

```bash
brew install --cask iterm2
```

* 安装 `rz` 和 `sz`

```bash
brew install lrzsz
```

* sz 即使send Zmodem，就是用Zmodem文件传输协议从Linux服务器发送文件

`vim /usr/local/bin/iterm2-send-zmodem.sh`

```vim
#!/bin/bash

osascript -e 'tell application "iTerm2" to version' > /dev/null 2>&1 && NAME=iTerm2 || NAME=iTerm
if [[ $NAME = "iTerm" ]]; then
	FILE=$(osascript -e 'tell application "iTerm" to activate' -e 'tell application "iTerm" to set thefile to choose folder with prompt "Choose a folder to place received files in"' -e "do shell script (\"echo \"&(quoted form of POSIX path of thefile as Unicode text)&\"\")")
else
	FILE=$(osascript -e 'tell application "iTerm2" to activate' -e 'tell application "iTerm2" to set thefile to choose folder with prompt "Choose a folder to place received files in"' -e "do shell script (\"echo \"&(quoted form of POSIX path of thefile as Unicode text)&\"\")")
fi

if [[ $FILE = "" ]]; then
	echo Cancelled.
	# Send ZModem cancel
	echo -e \\x18\\x18\\x18\\x18\\x18
	sleep 1
	echo
	echo \# Cancelled transfer
else
	cd "$FILE"
	/usr/local/bin/rz -E -e -b --bufsize 4096
	sleep 1
	echo
	echo
	echo \# Sent \-\> $FILE
fi
```

* rz 则就是receive Zmodem，从字面就很容易理解是在Linux上接收文件，也就是上传文件

`vim /usr/local/bin/iterm2-recv-zmodem.sh`

```vim
#!/bin/bash

osascript -e 'tell application "iTerm2" to version' > /dev/null 2>&1 && NAME=iTerm2 || NAME=iTerm
if [[ $NAME = "iTerm" ]]; then
	FILE=`osascript -e 'tell application "iTerm" to activate' -e 'tell application "iTerm" to set thefile to choose file with prompt "Choose a file to send"' -e "do shell script (\"echo \"&(quoted form of POSIX path of thefile as Unicode text)&\"\")"`
else
	FILE=`osascript -e 'tell application "iTerm2" to activate' -e 'tell application "iTerm2" to set thefile to choose file with prompt "Choose a file to send"' -e "do shell script (\"echo \"&(quoted form of POSIX path of thefile as Unicode text)&\"\")"`
fi
if [[ $FILE = "" ]]; then
	echo Cancelled.
	# Send ZModem cancel
	echo -e \\x18\\x18\\x18\\x18\\x18
	sleep 1
	echo
	echo \# Cancelled transfer
else
	/usr/local/bin/sz "$FILE" --escape --binary --bufsize 4096
	sleep 1
	echo
	echo \# Received $FILE
fi
```

* 修改权限

```bash
chmod 0755 /usr/local/bin/iterm2-*
```
* 设置Iterm2的Tirgger特性，profiles->default->editProfiles->Advanced中的Tirgger

添加两条trigger，分别设置 Regular expression，Action，Parameters，Instant如下：
```
1.第一条
        Regular expression: rz waiting to receive.\*\*B0100
        Action: Run Silent Coprocess
        Parameters: /usr/local/bin/iterm2-send-zmodem.sh
        Instant: checked
2.第二条
        Regular expression: \*\*B00000000000000
        Action: Run Silent Coprocess
        Parameters: /usr/local/bin/iterm2-recv-zmodem.sh
        Instant: checked
```

## Oh My Zsh 配置

* 安装 zsh 包管理器与其他依赖

```bash
brew install antigen autojump thefuck git-extras hr 
```

* 修改 zsh 配置文件

`vim ~/.zshrc`

* 刷新环境变量

`source .zshrc`

## SSH 目录权限

* .ssh 目录权限一般为 755 或者 700
* rsa_id.pub 及 authorized_keys 权限一般为 644
* rsa_id 权限必须为 600
