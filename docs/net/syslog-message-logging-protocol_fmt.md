# 系统日志消息记录协议

> 原文: [https://www.geeksforgeeks.org/syslog-message-logging-protocol/](https://www.geeksforgeeks.org/syslog-message-logging-protocol/)

`Syslog` 是消息日志记录的标准。`Syslog` 协议用于系统管理、系统审计、一般信息分析和调试。

## `Syslog` 协议基本上使用三层

1.  **系统日志内容–**
    系统日志内容是系统数据包中有效负载的信息。
2.  **系统日志应用程序–**
    它分析和处理系统日志消息的生成、解释、路由和存储。
3.  **`Syslog` Transport –**
    `Syslog` Transport 负责传输消息。

## 系统日志中的功能在 5 层执行

*   **发起者–**
    发起者是生成消息的本地机器。
*   **收集器–**
    收集器收集系统日志内容进行分析。它基本上是系统日志服务器。
*   **中继–**
    中继基本上将消息从发起者或其他中继转发到收集器或其他中继。
*   **传输发送方–**
    它将系统日志消息传输到传输协议，最常见的是 `UDP`。
*   **传输接收器–**
    它从指定的传输协议接收消息。

**消息组件:**
在信息头中，在传递给系统日志接收器之前添加的信息:

*   发起人流程标识
*   事件起源时间的时间戳。
*   发起方的 `IP` 地址。
*   发起人提供的信息包括设施代码和严重程度。

**设施代码:**
设施值指示哪个进程创建了系统日志消息。系统日志协议最初是在 `DSB Unix` 上编写的，因此设施值反映了 `Unix` 进程和守护进程的名称。

| 值 | 关键字 | 描述 |
| --- | --- | --- |
| `Zero` | `kern` | 内核消息 |
| `one` | `user` | 用户级消息 |
| `Two` | `mail` | 邮件系统 |
| `three` | `daemon` | 系统守护程序 |
| `four` | `auth` | 安全/授权消息 |
| `five` | `syslog` | 系统日志内部生成的消息 |
| `six` | `lpr` | 行式打印机子系统 |
| `seven` | `news` | 网络新闻子系统 |
| `eight` | `uucp` | `UUCP` 子系统 |
| `nine` | `cron` | 时钟守护程序 |
| `Ten` | `authpriv` | 安全/授权消息 |
| `Eleven` | `ftp` | `FTP` 守护程序 |
| `Twelve` | `ntp` | `NTP` 子系统 |
| `Thirteen` | `logaudit` | 日志审计 |
| `Fourteen` | `logalert` | 日志提醒 |
| `Fifteen` | `clock` | 时钟守护程序 |
| `Sixteen` | `local0` | 本地使用 0 (`local0`) |
| `Seventeen` | `local1` | 本地使用 1 (`local1`) |
| `Eighteen` | `local2` | 本地使用 2 (`local2`) |
| `Nineteen` | `local3` | 本地使用 3 (`local3`) |
| `Twenty` | `local4` | 本地使用 4 (`local4`) |
| `Twenty-one` | `local5` | 本地使用 5 (`local5`) |
| `Twenty-two` | `local6` | 本地使用 6 (`local6`) |
| `Twenty-three` | `local7` | 本地使用 7 (`local7`) |

**系统日志严重级别:**
设施值指示哪个进程创建了系统日志消息。系统日志协议最初是在 `DSB Unix` 上编写的，因此设施值反映了 `Unix` 进程和守护进程的名称。

| 值 | 严重级别 | 关键字 | 描述 |
| --- | --- | --- | --- |
| `Zero` | 紧急 | `emerg` | 系统不可用 |
| `one` | 警报 | `alert` | 应立即纠正 |
| `Two` | 严重 | `crit` | 临界条件 |
| `three` | 错误 | `err` | 错误条件 |
| `four` | 警告 | `warning` | 可能表示如果不采取措施，将会出现错误。 |
| `five` | 注意 | `notice` | 异常但不是错误情况的事件 |
| `six` | 信息 | `info` | 不需要任何操作的正常操作消息。 |
| `seven` | 调试 | `debug` | 对开发人员调试应用程序有用的信息。 |