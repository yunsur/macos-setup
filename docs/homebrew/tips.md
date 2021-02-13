# 常见问题

> 一些常见问题的解决办法

## 权限问题

* 错误信息

```bash
Error: The following directories are not writable by your user:
/usr/local/share/man/man8
You should change the ownership of these directories to your user.
sudo chown -R $(whoami) /usr/local/share/man/man8
```

* 解决办法

```bash
sudo chown -R `whoami`:admin /usr/local/bin
sudo chown -R `whoami`:admin /usr/local/share
```
