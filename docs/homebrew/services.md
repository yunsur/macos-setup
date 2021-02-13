# Homebrew Services

> Homebrew Services 集成 macOS 的 `launchctl` 管理器。可以进行启动、重启和停止等操作。

## Homebrew Services 用法

* 启动

```bash
brew services start <formula>
```

* 启动所有可用的服务

```bash
brew services start --all
```

* 运行

```bash
brew services run <formula>
```

* 停止

```bash
brew services stop <formula>
```

* 重启

```bash
brew services restart <formula>
```

* 列表

```bash
brew services list
```

* 清理

```bash
brew services cleanup
```
