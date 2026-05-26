# LAMP、MAMP 和 WAMP 栈的区别

> 原文：[https://www.geeksforgeeks.org/what-is-the-difference-between-lamp-stack-mamp-stack-and-wamp-stack/](https://www.geeksforgeeks.org/what-is-the-difference-between-lamp-stack-mamp-stack-and-wamp-stack/)

一个**网络栈**或者**网络应用栈**指的是一个软件的汇编，一起被用来建立网站或者网络应用。

构建一个栈的基本要求是：
1.  `operating system`
2.  `web server`
3.  `database`
4.  `Script interpreter`

## LAMP 栈

**LAMP** 栈是 **Linux** 操作系统、**Apache** Server、**MySQL** 数据库、**PHP** 的集合。**LAMP** 基本上就是你需要来创建一个动态网站和 web 应用的软件的集合。这些工具足够强大，你不需要任何其他工具来实现这个目的。**LAMP** 有趣的是里面所有的工具都是**免费开源的**。

*   **Linux:** 开源 `operating system`，管理系统硬件和应用程序。自 20 世纪 90 年代以来就已存在。它运行着大部分的互联网、证券交易所和财富 500 强超级计算机。它是最安全、最可靠的操作系统之一。**甚至 Android 也是由 Linux 驱动的。**
*   **Apache:** 一个免费、跨平台且开源的 web HTTP 服务器。Apache web 服务器，简称 Apache，在其全球发展后已成为最受欢迎的 web 服务器。Apache 处理用户请求并相应地响应适当的内容。它使用像 `HTTP` 或 `HTTPS` 这样的协议，这些实际上是互联网上服务器和客户端之间最重要的通信协议。`Hypertext Transfer Protocol` 只是一个定义消息如何在网络上传输和格式化的指令。然而，`HTTP` 以**明文**传输数据，`HTTPS` 以**加密**方式传输数据，后者更安全且值得推荐，这也是它被称为 `hypertext transfer protocol security` 的原因。`HTTP` 使用端口 80，`HTTPS` 使用端口 443。
*   **MySQL:** `MySQL` 是一个基于**关系模型**的 `SQL database`。在关系模型中，数据以行和列的形式存储在表中。非常适用于大型或小型应用程序。由 **Oracle** 支持开发。你可以通过查询来创建、修改或维护数据库中的数据。
*   **PHP:** 一种 `server-side scripting language`，它与服务器和数据库通信，并根据用户请求提供动态内容。`PHP` 和 `MySQL` 一直是一个致命的组合，也是当时最受欢迎的组合。它用于 PHP 后端网络开发，但也得到了升级。现在你可以在 `PHP` 中创建类和对象（`OOP` - 面向对象编程）。

### LAMP 栈工作原理

**浏览器**从**网络服务器（Apache）** 请求**特定网页**或**动态内容**，网络服务器将该请求传递给使用的**服务器端技术（PHP）**。如果需要，它又与**数据库（MySQL）** 通信，并选择特定的用户数据，将其转换为浏览器可以理解的 HTML，服务器将数据作为响应传递回浏览器。网络服务器运行在任何**操作系统（Linux）** 上。

## WAMP 栈

**Windows、Apache、MySQL** 和 **PHP** 一般缩写为 **WAMP**。有些人可能会和 **LAMP** 混淆，但两者唯一的区别就是操作系统。在 LAMP 的情况下，L 代表 Linux。设置服务器包括安装缩写中列出的所有软件。另一个版本是 **MAMP**，这是给 Mac 的。

*   **Windows OS:** 由 Microsoft 于 **1983 年 11 月 10 日**发布，它是一个基于 GUI 的操作系统，可以帮助客户端与硬件和其他软件程序通信、创建和删除文件和文件夹、存储数据以及做更多的事情！
*   **Apache:** 它是一个 `web server`，世界上 60% 的服务器机器都在使用。Apache web 服务器由 Apache Software Foundation 开发。
*   **MySQL:** 是一个由 Oracle 开发、基于 `RDBMS`（关系数据库管理系统）的 `SQL`（结构化查询语言）。
*   **PHP:** 是一种用于 `server` 的 `scripting language`，用于与 `server` 和 `database` 通信，并从数据库获取数据并呈现给用户。它对动态网站具有重要意义。

### WAMP 栈工作原理

与 LAMP 栈类似，**客户机请求**一个由**网络服务器（Apache）** 和服务器端脚本语言（PHP）处理的网站，用于给网站一种动态的感觉。而服务器运行在 Windows 操作系统上。

## MAMP 栈

**MAMP 栈**是 **MacOS、Apache Server、MySQL Database、PHP** 的集合。类似于 **WAMP** 和 **LAMP**，显著的区别是**操作系统**，这里我们使用 **MacOS**。可以轻松安装在基于 Mac 的系统上。它提供了在系统上运行 WordPress 等应用程序的能力。

*   **Mac OS:** 是一个基于图形用户界面的 `operating system`，由 Apple 公司开发并于 1984 年发布，用于 Apple Computer 的 Macintosh 系列个人计算机和工作站。

### MAMP 栈工作原理

类似于上面描述的栈，但是 **MAMP 栈**使用 **MacOS** 作为操作系统。

## LAMP、WAMP、MAMP 栈的区别

| 基础 | LAMP | WAMP | MAMP |
| :--- | :--- | :--- | :--- |
| **操作系统** | Linux | Windows | Mac OS |
| **Web 服务器** | Apache | Apache | Apache |
| **数据库** | MySQL | MySQL | MySQL |
| **脚本语言** | PHP | PHP | PHP |
| **多语言支持** | PHP, Python | PHP, Python | PHP, Python |