# Trafodion 和 Valentina 服务器的区别

> 原文: [https://www.geeksforgeeks.org/difference-between-trafodion-and-valentina-server/](https://www.geeksforgeeks.org/difference-between-trafodion-and-valentina-server/)

## 1. Trafodion
这是一个事务性的数据库管理系统。这是一个基于 `Hadoop` 的网络级 `SQL` 解决方案，支持 `Apache Hadoop` 上的事务性或操作性工作负载。“`Trafodion`”这个名字发音为“Tra-vod-eee-on”。它是一个运行在 `Apache Hadoop` 上的关系数据库管理系统，使用并行感知查询优化器为大数据环境中的事务性或操作性工作负载以及大型数据集提供支持。

## 2. Valentina 服务器
它是一个对象关系数据库和报表服务器以及快速对象关系数据库服务器。它是一个功能齐全、符合标准的基于 `SQLite` 的多用户访问数据库服务器。它包括集成数据库服务器，`Valentina` 数据库服务器和 `SQLite` 数据库服务器。

## Trafodion 和 Valentina 服务器的区别

```
| 编号 | Trafodion | Valentina 服务器 |
| --- | --- | --- |
| 1 | 由 `Apache` 软件基金会开发，最初由惠普开发，最初于 2014 年发布。 | 由 `Paradigma` 软件开发，最初于 1994 年发布。 |
| 2 | 目前发布于 2019 年 2 月。 | `Valentina Server` 的当前版本是 5.7.5。 |
| 3 | `Linux` 是 `Trafodion` 的服务器操作系统。 | `Linux`、`OS X`、`Windows` 都是 `Valentina` 服务器的服务器操作系统。 |
| 4 | 主要的数据库模型是关系数据库管理系统。 | 主要的数据库模型是关系数据库管理系统。 |
| 5 | 支持 `JDBC/ODBC/ADO.NET` 的所有语言。`.Net` 是编程语言。 | `.Net`、`C`、`C#`、`C++`、`Objective-C`、`PHP`、`Ruby`、`Visual Basic`、`Visual Basic.NET` 都是支持编程的语言。 |
| 6 | `ADO.NET`、`JDBC`、`ODBC` 是 `Trafodion` 的 `API` 和其他访问方法。 | `Valentina` 服务器支持 `ODBC` `API` 和其他访问方法。 |
| 7 | 事务有数据模式。 | 它也有数据模式。 |
| 8 | 它有实现语言 `Java` 和 `C++`。 | 它没有任何实现语言。 |
| 9 | `Trafodion` 有 `ACID` 事务概念。 | 它没有事务概念。 |
| 10 | 通过 `HBase` 是 `Trafodion` 的复制方法。 | `Valentina` 服务器中缺少复制方法。 |
| 11 | `Trafodion` 持有即时一致性概念。 | `Valentina` 服务器没有一致性概念。 |
```