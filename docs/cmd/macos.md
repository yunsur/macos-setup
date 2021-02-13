# macOS 命令

> 常用命令行工具

## 刷新 DNS 缓存

```sh
sudo dscacheutil -flushcache; sudo killall -HUP mDNSResponder
```

## 校验 md5 / sha1 / sha256 / crc32 值

```sh
# 计算 md5 值
md5 mysql-workbench-community-6.3.10-macos-x86_64.dmg
# 输出结果
MD5 (mysql-workbench-community-6.3.10-macos-x86_64.dmg) = 4ad59ce1e00ab51fe33e23131cda29ce

# 计算 sha1 值
shasum -a1 mysql-workbench-community-6.3.10-macos-x86_64.dmg
9b0b3f870f3f87904decda22dd75c75b5fe35613  mysql-workbench-community-6.3.10-macos-x86_64.dmg

# 计算 sha256 值
shasum -a256 mysql-workbench-community-6.3.10-macos-x86_64.dmg
ae1b00b205db99515b8edd09e58d34741b173891fc987fdbcb88de6bc74f2622  mysql-workbench-community-6.3.10-macos-x86_64.dmg

# 计算 crc32 值
crc32 mysql-workbench-community-6.3.10-macos-x86_64.dmg
3cdb5c6
```

## 禁止 .DS_store 生成

.DS_Store 是 Mac OS 保存文件夹的自定义属性的隐藏文件，如文件的图标位置或背景色，相当于 Windows 的 desktop.ini。

* 禁止.DS_store生成:

```sh
defaults write com.apple.desktopservices DSDontWriteNetworkStores -bool TRUE
```

* 恢复.DS_store生成：

```sh
defaults delete com.apple.desktopservices DSDontWriteNetworkStores
```

## 反编译 APK

* APK 反编译、打包、签名

```sh
https://ibotpeaches.github.io/Apktool/install/
```

* 解压安装包

```sh
apktool decode hellophonegap.apk
```

* 打包压缩包

```sh
apktool build hellophonegap -o hellophonegap-new.apk
```

* 生成证书

```sh
keytool -genkey -alias {name} -keyalg RSA -validity 20000 -keystore {name}.keystore
```

* 开始签名

```sh
jarsigner -storepass 123456 -digestalg SHA1 -sigalg SHA1withRSA -tsa http://timestamp.wosign.com/timestamp -verbose -keystore ./{name}.keystore -signedjar ./hellophonegap-signed.apk ./hellophonegap.apk {name}
```

* 验证签名

```sh
jarsigner -verify -verbose -certs hellophonegap-signed.apk
```
