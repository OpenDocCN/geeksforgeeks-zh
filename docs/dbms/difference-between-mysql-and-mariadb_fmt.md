# MySQL 和 MariaDB 的区别

> 原文：[`https://www.geeksforgeeks.org/difference-between-mysql-and-mariadb/`](https://www.geeksforgeeks.org/difference-between-mysql-and-mariadb/)

## 1. MySQL

`MySQL` 是基于结构化查询语言（`SQL`）的开源关系数据库管理系统（`RDBMS`）。它由甲骨文公司开发和管理，最初于 1995 年 5 月 23 日发布。它被广泛用于许多小型和大型工业应用中，并且能够处理大量数据。在甲骨文收购 `MySQL` 后，数据库的使用出现了一些问题，于是开发了 `MariaDB`。

## 2. MariaDB

`MariaDB` 是一个开源的关系数据库管理系统（`RDBMS`），是广泛使用的 `MySQL` 数据库技术的兼容插件替代。它由马里亚数据库基金会开发，最初于 2009 年 10 月 29 日发布。`MariaDB` 有大量新功能，这使得它在性能和面向用户方面比 `MySQL` 更好。

## MySQL 和 MariaDB 的区别

| 编号 | MySQL | MariaDB |
| :--- | :--- | :--- |
| 1. | `MySQL` 是用 `C` 和 `C++` 语言编写的。 | `MariaDB` 是用 `C`、`C++`、`Perl` 和 `Bash` 语言编写的。 |
| 2. | 最初发布于 1995 年。 | 最初发布于 2009 年。 |
| 3. | 和 `MariaDB` 相比，`MySQL` 的性能并没有那么出色。 | `MariaDB` 的性能远胜于 `MySQL`。 |
| 4. | 它没有为 `MariaDB` 提供替代品。 | 它为 `MySQL` 提供了一个插件替代。 |
| 5. | 数据屏蔽在 `MySQL` 中完成。 | 没有数据屏蔽。 |
| 6. | 专有代码可在 `MySQL` 企业版中访问。 | 专有代码在 `MariaDB` 中不可访问。 |
| 7. | 不支持二进制日志或临时表空间。 | 支持临时表空间和二进制加密。 |
| 8. | 不能轻松处理大规模数据。 | 可以轻松处理大规模数据。 |
| 9. | 权限检查在 `MySQL` 中没有那么快。 | 权限检查在 `MariaDB` 中完成得更快。 |
| 10. | `MySQL` 有 1600 个叉。 | `MariaDB` 有 868 个叉子。 |
| 11. | Airbnb、Pinterest、Slack、Udemy、Twitter 等知名公司使用 `MySQL`。 | 像纽约市立大学、埃森哲、Docplanner、Grooveshark、诺斯罗普·格鲁曼等知名公司都使用 `MariaDB`。 |
| 12. | `MySQL` 的服务器操作系统是 FreeBSD，Linux，OS X，Solaris，Windows 也就是说 `MySQL` 中支持 OS X 作为服务器。 | 的服务器操作系统为 FreeBSD、Linux、Solaris、Windows，即 `MariaDB` 不支持 OS X 作为服务器。 |