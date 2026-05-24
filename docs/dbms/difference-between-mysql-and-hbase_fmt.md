# MySQL 和 HBase 的区别

> 原文: [https://www.geeksforgeeks.org/difference-between-mysql-and-hbase/](https://www.geeksforgeeks.org/difference-between-mysql-and-hbase/)

## 1. MySQL
`MySQL` 是基于[结构化查询语言(`SQL`)](https://www.geeksforgeeks.org/structured-query-language/) 的开源关系数据库管理系统。它由甲骨文公司开发和管理，最初于 1995 年 5 月 23 日发布。它被广泛用于许多小型和大型工业应用中，并且能够处理大量数据。

## 2. HBase
该模型用于提供对大量结构化数据的随机访问。它建立在 `Hadoop` 文件系统之上，本质上是面向列的。它曾经在 `HDFS` 存储数据。提供数据复制的是开源数据库。`HBase` 的三个重要组成部分是主机、区域服务器和动物园管理员。

### MySQL 和 HBase 的区别

| **MySQL** 的实现 | **HBase** |
| --- | --- |
| `MySQL` 管理结构化数据。 | `HBase` 管理结构化数据，非结构化数据。 |
| 它需要结构化的查询语言。 | 它不需要结构化查询语言。 |
| `MySQL` 支持的操作系统有 `Windows`、`macOS`、`Linux`、`Unix`、`AmigaOS`、`BSD`、`z/OS`、`Android`。 | `HBase` 支持的操作系统有 `Windows`、`macOS`、`Linux`、`Unix`、`BSD`、`z/OS`。 |
| 它遵循 `ACID` 属性。 | 它不遵循 `ACID` 属性。 |
| 这里使用的复制方法有主-主复制和主-从复制。 | 这里使用的复制方法是主从复制。 |
| 它是用 `C/C++` 编程语言实现的。 | 它是用 `Java` 编程语言实现的。 |
| `MySQL` 支持的语言有 `C`、`C#`、`C++`、`Python`、`Ruby`、`Java`、`PHP`、`Javascript` 等。 | `HBase` 支持的语言是 `Java`。 |
| 它处理的数据量较少。 | 它处理大量数据。 |
| 支持的辅助数据库模型是文档存储。 | 没有使用辅助数据库模型。 |
| `MySQL` 使用的 `API` 和其他访问方法有 `ADO.NET`、`JDBC` 和 `ODBC`。 | `HBase` 使用的 `API` 和其他访问方法是 `JDBC`。 |