# SMTP 命令

> 原文: [https://www.geeksforgeeks.org/smtp-commands/](https://www.geeksforgeeks.org/smtp-commands/)

[简单邮件传输协议(SMTP)](https://www.geeksforgeeks.org/simple-mail-transfer-protocol-smtp/) 是一种 ASCII 协议。它基于客户机-服务器模式。该服务使用 TCP 端口号 `25`。因此，电子邮件通过让源机器建立到目的机器的端口 `25` 的 TCP，从源传送到目的机器。要发送邮件，系统必须包含客户端 MTA，要接收邮件，系统必须有服务器 MTA。SMTP 将此邮件从客户端 MTA 传输到服务器 MTA。要发送邮件，SMTP 使用两次：一次在发件人和发件人的邮件服务器之间，另一次在两个邮件服务器之间。

## SMTP 命令

这些命令从**客户端发送到服务器**。每个命令由一个关键字和零个或多个参数组成。这意味着也有一些关键字不包含任何参数。该命令的格式如下：

```
Keywords : argument(s)
```

有 14 个不同的 SMTP 命令，如下表所示：

<figure class="table">

| 序列号 | 关键词 | 命令表单 | 描述 | 用法 |
| :--- | :--- | :--- | :--- | :--- |
| 1. | `HELO` | `HELO <sp><domain><crlf>` | 它提供发送方的标识，即主机名。 | 命令的 |
| 2. | `MAIL` | `MAIL <sp>FROM:<reverse-path><crlf>` | 它指定邮件的发件人。 | 命令的 |
| 3. | `RCPT` | `RCPT <sp>TO:<forward-path><crlf>` | 它指定邮件的收件人。 | 命令的 |
| 4. | `DATA` | `DATA<crlf>` | 它指定邮件的开头。 | 命令的 |
| 5. | `QUIT` | `QUIT<crlf>` | 它会关闭 TCP 连接。 | 命令的 |
| 6. | `RSET` | `RSET<crlf>` | 它中止当前的邮件事务，但 TCP 连接保持打开。 | 强烈推荐 |
| 7. | `VRFY` | `VRFY<crlf>` | 它用于确认或验证用户名。 | 强烈推荐 |
| 8. | `NOOP` | `NOOP<crlf>` | 无操作 | 强烈推荐 |
| 9. | `TURN` | `TURN<crlf>` | 它颠倒了发送者和接收者的角色。 | 很少使用 |
| 10. | `EXPN` | `EXPN<crlf>` | 它指定要扩展的邮件列表。 | 很少使用 |
| 11. | `HELP` | `HELP<crlf>` | 它向系统发送一些特定的文档。 | 很少使用 |
| 12. | `SEND` | `SEND <sp>FROM:<reverse-path><crlf>` | 它向终端发送邮件。 | 很少使用 |
| 13. | `SOML` | `SOML <sp>FROM:<reverse-path><crlf>` | 如果可能的话，它向终端发送邮件；否则发送到邮箱。 | 很少使用 |
| 14. | `SAML` | `SAML <sp>FROM:<reverse-path><crlf>` | 它向终端和邮箱发送邮件。 | 很少使用 |

</figure>