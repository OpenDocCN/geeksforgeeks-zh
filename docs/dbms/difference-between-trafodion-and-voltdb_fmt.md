# Trafodion 和 VoltDB 的区别

> 原文：[https://www.geeksforgeeks.org/difference-between-trafodion-and-voltdb/](https://www.geeksforgeeks.org/difference-between-trafodion-and-voltdb/)

## 1. Trafodion
这是一个事务性的数据库管理系统。这是一个基于 Hadoop 的网络级 SQL 解决方案，支持 Apache Hadoop 上的事务性或操作性工作负载。“Trafodion”这个名字发音为“Tra-vod-eee-on”。它是一个运行在 Apache Hadoop 上的关系数据库管理系统，使用并行感知查询优化器为大数据环境中的事务性或操作性工作负载以及大型数据集提供支持。

## 2. VoltDB
它是一个符合 `ACID` 标准的关系数据库管理系统和分布式内存中的 NewSQL 关系数据库管理系统，使用的是一个无共享架构。由迈克尔·斯通布雷克、萨姆·马登和丹尼尔·阿巴迪设计的数据库。最初，VoltDB 数据库包括集群吞吐量和延迟以及 CPU 和内存使用情况的图表。它基于 H-Store，并随着多核服务器上每 CPU 内核数量的增加而扩展。

## Trafodion 和 VoltDB 的区别

| 编号 | Trafodion | VoltDB |
| :--- | :--- | :--- |
| 1 | 由 Apache 软件基金会开发，最初由惠普开发，最初于 2014 年发布。 | 由 VoltDB Inc. 开发，最初于 2010 年发布。 |
| 2 | 目前发布于 2019 年 2 月。 | 目前发布于 2019 年 4 月。 |
| 3 | Linux 是服务器，Trafodion 的操作系统。 | Linux、OS X 都是 VoltDB 的服务器操作系统。 |
| 4 | 主要的数据库模型是关系数据库管理系统。 | 主要的数据库模型是关系数据库管理系统。 |
| 5 | 支持 `JDBC`/`ODBC`/`ADO.NET` 是编程语言。 | `C#`、`C++`、`Erlang`、`Go`、`Java`、`JavaScript`、`PHP`、`Python` 都是支持编程的语言。 |
| 6 | `ADO.NET`、`JDBC`、`ODBC` 是 Trafodion 的 `API` 和其他访问方法。 | `Java API`、`JDBC`、`RESTful HTTP/JSON API` 都是 `API` 等访问方式。 |
| 7 | 事务有数据模式。 | 它也有数据模式。 |
| 8 | 它有实现语言 `Java` 和 `C++`。 | VoltDB 的实现语言是 `Java`，`C++`。 |
| 9 | Trafodion 有 `ACID` 事务概念。 | `ACID`（原子性、一致性、隔离性和持久性）是事务概念。 |
| 10 | 通过糖化血红蛋白是交通的复制方法。 | VoltDB 的复制方式有主从复制和主从复制。 |
| 11 | Trafodion 持有即时一致性概念。 | 它没有一致性概念。 |
| 12 | 它有外键的概念。 | 它也有外键的概念。 |