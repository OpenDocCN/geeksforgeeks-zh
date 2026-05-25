# 思科路由器模式

> 原文: [https://www.geeksforgeeks.org/cisco-router-modes/](https://www.geeksforgeeks.org/cisco-router-modes/)

路由器是第 3 层设备，用于将数据包从一个网络转发到另一个网络。它根据目的 IP 地址和路由表中的条目，通过其中一个端口转发数据包。通过使用路由表，它可以找到源网络和目的网络之间的优化路径。

让我们讨论思科路由器的不同模式。

## 路由器的模式

路由器主要有 5 种模式：

### 用户执行模式

界面弹出消息一出现，按回车键，就会弹出`路由器>`提示。这被称为用户执行模式。此模式仅限于某些监控命令。

### 特权模式

当我们在用户模式下输入`enable`时，我们进入特权模式，在该模式下我们可以查看和更改路由器的配置。不同的命令，如`show running-config`、`show ip interface brief`等，可以在此模式下运行，用于故障排除。

### 全局配置模式

当我们输入`configure terminal`到用户模式时，我们将进入全局配置模式。在这些模式下输入的命令称为全局命令，它们会影响路由器的运行配置。在这种模式下，不同的配置，如通过提供用户名和密码在路由器上创建本地数据库，可以设置`enable`密码等。

### 界面配置模式

在该模式下，只进行界面的配置。为接口分配一个 IP 地址，调出接口是这种模式下常见的任务。

### ROMMON 模式

我们可以在中断路由器的启动过程时进入这个模式。通常，在密码恢复过程或在 TFTP 服务器等设备上备份 IOS 时，我们会进入此模式。这就像电脑的 BIOS 模式。

## 不同模式进出

| 模式 | 存取方法 | 提示 | 退出方法 |
| :--- | :--- | :--- | :--- |
| 用户执行模式 | 注册 | `路由器>` | 使用`logout`命令 |
| 特权模式 | 在用户模式下使用`enable`命令 | `路由器#` | 使用`disable`命令进入用户模式 |
| 全局配置模式 | 使用`configure terminal`命令 | `路由器(config)#` | 使用`exit`命令进入特权模式 |
| 界面模式 | 使用`interface`命令并在全局配置模式下指定一个接口 | `路由器(config-if)#` | 使用`exit`命令进入全局配置模式，或使用`end`命令进入特权模式。 |
| ROMMON 模式 | 启动过程中按`ctrl+break`键，或在特权模式下使用`reload`命令。 | `ROMMON 1 >` | 使用`continue`命令 |

## 配置示例

用户执行模式：

```
router>
```

从用户执行模式进入特权模式：

```
router>enable
router#
```

从特权模式退出到用户执行模式：

```
router#disable
router>
```

从特权模式进入全局配置模式：

```
router#configure terminal
router(config)#
```

从全局配置模式退出到特权模式：

```
router(config)#exit
router#
```

从全局配置模式进入接口模式。这里我们必须指定路由器的接口。

```
router(config)#interface fa0/0
router(config-if)#
```

从接口模式退出到全局配置模式。

```
router(config-if)#exit
router(config)#
```

从接口模式退出到特权模式。

```
router(config-if)#end
router#
```

从特权模式进入 ROMMON 模式。

```
router#reload
```