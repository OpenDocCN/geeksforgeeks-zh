# 【LAMP、MAMP 和 WAMP 栈的区别

> 原文:[https://www . geesforgeks . org/lamp-stack-mamp-stack-wamp-stack/](https://www.geeksforgeeks.org/what-is-the-difference-between-lamp-stack-mamp-stack-and-wamp-stack/)区别是什么

一个**网络栈**或者**网络应用栈**指的是一个软件的汇编，一起被用来建立网站或者网络应用。

构建一个栈的基本要求是:

1.  operating system
2.  web server
3.  database
4.  Script interpreter

**[**灯栈:**](https://www.geeksforgeeks.org/installing-php-and-configuring-it-on-ubuntu-14-04-trusty/)**

**LAMP** 栈是 **Linux 操作系统、Apache Server、MySQL 数据库、PHP** 的集合。 **LAMP** 基本上就是你需要来创建一个动态网站和 web 应用的软件的集合。 这些工具足够强大，你不需要任何其他工具来实现这个目的。 **LAMP** 有趣的是里面所有的工具都是 **免费开源的** 。

*   **Linux:** 管理系统硬件和应用的开源**操作系统**。从 20 世纪 90 年代就有了。它运行大部分互联网、股票交易所和世界 500 强超级计算机。它是最安全、最可靠的操作系统之一。**即使是安卓也是由 Linux 驱动的。**
*   **Apache:** 一个免费的、跨平台的、开源的 web HTTP 服务器。Apache 网络服务器或简称 Apache，在全球范围内发展后成为最受欢迎的网络服务器。Apache 处理用户请求，并相应地用合适的内容进行响应。它使用像 **HTTP 或 HTTPS** 这样的协议，这些协议实际上是互联网上服务器和客户端之间最重要的通信协议。**超文本传输协议**只不过是用来定义信息如何在网络上格式化和传输的指令。而 **HTTP** 以**纯文本** **传输数据，HTTPS** 采用**加密**传输数据，更安全，更推荐，这也是为什么被称为**超文本传输协议安全的原因。HTTP** 有端口 80， **HTTPS** 有端口 443。
*   **MySQL: MySQL** 是一个基于**关系模型**的 **SQL 数据库**。在关系模型中，数据以行和列的形式存储在表中。非常适合大型或小型应用。由**甲骨文开发支持。**您可以通过查询在数据库中创建、修改或维护您的数据。
*   **PHP:** 一种**服务器端脚本语言**，与服务器和数据库通信，并根据用户请求提供动态内容。 **PHP 和 MySQL** 是一个致命的组合，也是当时最受欢迎的组合。PHP 用于后端网络开发，但也有升级，现在你可以在 **PHP 中创建类和对象。****(OOP——面向对象编程)。**

**灯组工作:**

**浏览器**从**网络服务器(Apache)** 请求特定的**网页**或**动态内容**，网络服务器将该请求传递给**服务器端技术**使用的 **(Php)** 。如果需要，它又与**数据库(Mysql)** 通信，并选择特定的用户数据，将其转换为浏览器可以理解的 HTML，服务器将数据作为响应传递回浏览器。网络服务器运行在任何**操作系统(Linux)** 上。

**[**WAMP 栈:**](https://www.geeksforgeeks.org/how-to-install-and-set-up-a-wamp-server/)T5】**

**Windows、Apache、MySQL** 、**和 PHP** 一般缩写为 **WAMP。** 有些人可能会和 **LAMP** 混淆，但两者唯一的区别就是操作系统。在LAMP 的情况下，L 代表 Linux。设置服务器包括安装缩写中列出的所有软件。另一个版本是 **MAMP，** 这是给 Mac 的。

*   [T0】 Windows OS: 【T1] Published by Microsoft on **November 10, 1983** It is an operating system based on GUI, which can help clients communicate with hardware and other software programs, create and delete files and folders, store data and do more things!
*   **Apache:** It is a **web server** used by 60% of server machines in the world. The Apache web server is developed by Apache Software Foundation.
*   **MySQL:** is a **SQL** (structured query language) developed by Oracle and based on **RDBMS** (relational database management system).
*   **PHP:** is a **scripting language** used in **server** , which is used to communicate with **server** and **database** , and obtain data from the database and present it to users. It is of great significance to dynamic websites.

**WAMP 堆栈工作:**

与 LAMP 栈类似，**客户机请求**一个由**网络服务器(Apache)** 和服务器端脚本语言(php)处理的网站，用于给网站一种动态的感觉。而服务器运行在Windows 操作系统上。

****MAMP 栈:****

**MAMP 栈**是 **MacOS、Apache Server、MySQL Database、PHP 的集合。**类似于 **WAMP** 和 **LAMP** 显著的区别是**操作系统**这里我们使用 **MacOS。** 可以轻松安装在基于 Mac 的系统上。它提供了在系统

*   All devices running [T1】 WordPress 【T2] on **Mac OS: Mac OS** is a **operating system** based on graphical user interface, which was developed by Apple Company and released in 1984 for Macintosh series personal computers and workstations of Apple Computer.

**MAMP 堆栈工作:**

类似于上面描述的堆栈，但是 **MAMP 堆栈**使用 **MacOS** 作为操作系统。

【LAMP、WAMP、MAMP 栈的区别:

<figure class="table">

| 基础 | 灯 | WAMP | MAMP |
| --- | --- | --- | --- |
| **操作系统** | Linux OS | Windows OS | macOS |
| **多语言** | Php、Python 或 Perl | Php | Php |

</figure>