# Trafodion 和 ToroDB 的区别

> 原文: [https://www.geeksforgeeks.org/difference-between-trafodion-and-torodb/](https://www.geeksforgeeks.org/difference-between-trafodion-and-torodb/)

## Trafodion

这是一个事务性的数据库管理系统。这是一个网络规模的 `Hadoop` 上的 `SQL` 解决方案，支持 `Apache Hadoop` 上的跨国或运营工作负载。“`Trafodion`”这个名字发音为“Tra-vod-eee-on”。它是一个运行在 `Apache Hadoop` 上的关系数据库管理系统，使用并行感知查询优化器为大数据环境中的跨国或运营工作负载以及大型数据集提供支持。

## ToroDB

它是一个 `MongoDB` 兼容的 `JSON` 文档存储，建立在 `PostgreSQL` 之上，是一种旨在填补面向文档和 `SQL` 数据库之间空白的技术。它是一个开源的 `NoSQL` 数据库，运行在与 `MongoDB` 协议和应用编程接口兼容的关系数据库管理系统之上。`ToroDB` 是一个开源项目，它读取 `NoSQL` 文档，自动推断其结构，并将其转换为一组表和列，这些表和列将数据表示为关系形式。

## Trafodion 和 ToroDB 的区别

```
| 编号 | Trafodion | ToroDB |
| --- | --- | --- |
| 1 | 由 `Apache` 软件基金会开发，最初由惠普开发，最初于 2014 年发布。目前发布于 2019 年 2 月。 | 由 `8Kdata` 开发，最初于 2016 年发布。 |
| 2 | `Linux` 是服务器，`Trafodion` 的操作系统。 | 所有带有 `Java 7` 虚拟机的操作系统都是服务器操作系统。 |
| 3 | 主要的数据库模型是关系数据库管理系统。 | 主要数据库模型是文档存储。 |
| 4 | 支持 `JDBC`/`ODBC`/`ADO.NET` 是编程语言。 | 没有任何支持的编程语言。 |
| 5 | `ADO.NET`、`JDBC`、`ODBC` 是 `Trafodion` 的 `API` 和其他访问方法。 | `ToroDB` 中缺少 `API` 和其他访问方法。 |
| 6 | 它有数据模式。 | 它具有无模式的数据模式。 |
| 7 | 它有实现语言 `Java` 和 `C++`。 | 它的实现语言是 `Java`。 |
| 8 | `Trafodion` 有 `ACID` 事务概念。 | 数据库中缺少事务概念。 |
| 9 | 通过 `HBase` 是 `Trafodion` 的复制方法。 | `ToroDB` 中的主从复制方法。 |
| 10 | 它包含即时一致性概念。 | 具有最终一致性和即时一致性的概念。 |
| 11 | 它持有外键。 | 不，它没有外键。 |
```