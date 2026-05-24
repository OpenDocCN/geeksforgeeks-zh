# Cassandra 和 MariaDB 的区别

> 原文: [https://www.geeksforgeeks.org/difference-between-cassandra-and-mariadb/](https://www.geeksforgeeks.org/difference-between-cassandra-and-mariadb/)

## 1. Cassandra
`Cassandra` 是一个免费开源的、分布式的、宽列存储的 `NoSQL` 数据库管理系统。它由 `Apache` 软件基金会开发，最初于 2008 年 7 月发布。`Cassandra` 旨在处理许多商用服务器上的大量数据，提供高可用性，没有单点故障。

## 2. MariaDB
`MariaDB` 是一个开源的关系数据库管理系统 (`RDBMS`)，是广泛使用的 `MySQL` 数据库技术的兼容插件替代。它由 `MariaDB` 基金会开发，最初于 2009 年 10 月 29 日发布。`MariaDB` 有大量的新功能，这使得它在性能和面向用户方面比 `MySQL` 更好。

## Cassandra 和 MariaDB 的区别

| 序号 | Cassandra | MariaDB |
| :--- | :--- | :--- |
| 1. | 由 `Apache` 软件基金会开发，于 2008 年 7 月发布。 | 由 `MariaDB Corporation Ab` 开发，并于 2009 年 10 月 29 日首次发布。 |
| 2. | `Cassandra` 仅用 `Java` 语言编写。 | `MariaDB` 是用 `C`、`C++`、`Perl` 和 `Bash` 语言编写的。 |
| 3. | `Cassandra` 不提供 `ACID` 事务，但可以进行调整以支持 `ACID` 属性。 | `MariaDB` 提供无快照隔离的 `ACID` 事务。 |
| 4. | `Cassandra` 支持选择性复制因子复制方法。 | `MariaDB` 支持主从复制和主-主复制复制方法。 |
| 5. | 在 `Cassandra` 中，没有外键的概念。 | `MariaDB` 提供了引用完整性的概念，并且有外键。 |
| 6. | `Cassandra` 支持 `MapReduce` 方法。 | `MariaDB` 不支持 `MapReduce` 方法。 |
| 7. | `Cassandra` 不支持 `XML` 数据格式。 | `MariaDB` 确实支持 `XML` 数据格式。 |
| 8. | `Cassandra` 仅粗略支持二级索引，即二级索引受到限制。 | `MariaDB` 确实支持二级索引的概念。 |
| 9. | `Cassandra` 的服务器操作系统是 `BSD`、`Linux`、`OS X`、`Windows`。 | `MariaDB` 的服务器操作系统有 `FreeBSD`、`Linux`、`Solaris`、`Windows`。 |
| 10. | 像 `GitHub`、`GoDaddy`、`Hulu`、`Instagram`、`Reddit`、天气频道等知名公司都使用 `Cassandra`。 | 纽约市立大学、埃森哲、`Docplanner`、纳斯达克、红帽、`ServiceNow` 等知名公司都使用 `MariaDB`。 |