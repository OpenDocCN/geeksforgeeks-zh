# MongoDB 和 MariaDB 的区别

> 原文: [https://www.geeksforgeeks.org/difference-between-mongodb-and-mariadb/](https://www.geeksforgeeks.org/difference-between-mongodb-and-mariadb/)

## MongoDB

`MongoDB` 是一个面向跨平台文档的非关系型（即 [`NoSQL`](https://www.geeksforgeeks.org/introduction-to-nosql/)）数据库程序。它是一个开源文档数据库，以键值对的形式存储数据。`MongoDB` 由 `MongoDB Inc.` 开发，最初于 2009 年 2 月 11 日发布。用 [`C++`](https://www.geeksforgeeks.org/c-plus-plus/)、[`Go`](https://www.geeksforgeeks.org/go-programming-language-introduction/)、[`JavaScript`](https://www.geeksforgeeks.org/javascript-tutorial/)、[`Python`](https://www.geeksforgeeks.org/python-programming-language/) 语言编写。`MongoDB` 提供了高速度、高可用性和高扩展性。

## MariaDB

`MariaDB` 是一个开源的关系数据库管理系统（`RDBMS`），是广泛使用的 `MySQL` 数据库技术的兼容插件替代。它由 `MariaDB Foundation` 开发，最初于 2009 年 10 月 29 日发布。`MariaDB` 有大量的新功能，这使得它在性能和面向用户方面比 [`MySQL`](https://www.geeksforgeeks.org/mysql-common-mysql-queries/) 更好。

## MongoDB 和 MariaDB 的区别

| 编号 | MongoDB | MariaDB |
| :--- | :--- | :--- |
| 1. | 由 `MongoDB Inc.` 开发，最初于 2009 年 2 月 11 日发布。 | 由 `MariaDB Corporation Ab` 开发。并于 2009 年 10 月 29 日首次发布。 |
| 2. | `MongoDB` 是用 `C++`、`Go`、`JavaScript`、`Python` 语言编写的。 | `MariaDB` 是用 `C`、`C++`、`Perl` 和 `Bash` 语言编写的。 |
| 3. | `MongoDB` 为多文档 `ACID` 事务提供快照隔离。 | `MariaDB` 只提供 `ACID` 事务，没有快照隔离。 |
| 4. | `MongoDB` 拥有支持系统中所有语言的庞大基础。 | `MariaDB` 不支持 `Matlab` 和 `shell` 语言。 |
| 5. | `MongoDB` 的工作方式不同于 `SQL`，但它根据用户在系统中的角色授予用户访问权限。 | `MariaDB` 有许多类似的查询，工作方式也类似于 `SQL`。 |
| 6. | `MongoDB` 没有提供引用完整性的概念。因此没有外键。 | `MariaDB` 提供了引用完整性的概念，并且有外键。 |
| 7. | `MongoDB` 支持的复制方法是主从复制。 | `MariaDB` 支持主从复制和主主复制。 |
| 8. | `MongoDB` 支持 `MapReduce` 方法。 | `MariaDB` 不支持 `MapReduce` 方法。 |
| 9. | `MongoDB` 的服务器操作系统有 `Solaris`、`Linux`、`OS X`、`Windows`。 | `MariaDB` 的服务器操作系统是 `FreeBSD`、`Linux`、`Solaris`、`Windows`。 |
| 10. | `Adobe`、`Amadeus`、`Lyft`、`ViaVarejo`、`Craftbase` 等知名公司都使用 `MongoDB`。 | 纽约市立大学、埃森哲、`Docplanner`、`Grooveshark`、诺斯罗普·格鲁曼等著名公司都使用 `MariaDB`。 |