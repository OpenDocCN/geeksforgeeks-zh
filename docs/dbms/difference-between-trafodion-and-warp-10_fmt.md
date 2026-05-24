# Trafodion 和 Warp 10 的区别

> 原文：[https://www.geeksforgeeks.org/difference-between-trafodion-and-warp-10/](https://www.geeksforgeeks.org/difference-between-trafodion-and-warp-10/)

## Trafodion
这是一个事务性的数据库管理系统。这是一个基于 `Hadoop` 的网络级 `SQL` 解决方案，支持 `Apache Hadoop` 上的事务性或操作性工作负载。“Trafodion”这个名字发音为“Tra-vod-eee-on”。它是一个运行在 `Apache Hadoop` 上的关系数据库管理系统，使用并行感知查询优化器为大数据环境中的事务性或操作性工作负载以及大型数据集提供支持。

## Warp 10
它是一个时间序列数据库管理系统，专门处理基于 `LevelDB` 或 `HBase` 的带时间戳的地理数据。Warp 10 的服务器操作系统是 `Linux`、`OS X`、`Windows`。它是最先进的时间序列平台。这是一个开源的地理时间序列平台，旨在监控系统和物联网，并处理来自传感器的数据。

## Trafodion 和 Warp 10 的区别

| 编号 | Trafodion | Warp 10 |
| :--- | :--- | :--- |
| 1 | 它由 `Apache` 软件基金会开发，最初由惠普开发，于 2014 年发布。 | 它由 `SenX` 开发，最初于 2015 年发布。 |
| 2 | `Linux` 是 `Trafodion` 的服务器操作系统。 | `Linux`、`OS X`、`Windows` 都是 `Warp 10` 中的服务器操作系统。 |
| 3 | 主要的数据库模型是关系数据库管理系统。 | 主要的数据库模型是时间序列数据库管理系统。 |
| 4 | 支持 `JDBC`/`ODBC`/`ADO.NET` 的所有语言。 | 在 `Warp 10` 中没有这种支持的编程语言。 |
| 5 | 它有数据模式。 | 它具有无模式的数据模式。 |
| 6 | 它的实现语言是 `Java` 和 `C++`。 | 它的实现语言是 `Java`。 |
| 7 | 它有 `ACID` 事务概念。 | `Warp 10` 中缺少事务概念。 |
| 8 | 通过 `HBase` 是 `Trafodion` 的复制方法。 | 可选择的复制因子是 `Warp 10` 的复制方法。 |
| 9 | 它包含即时一致性概念。 | 它有最终一致性的概念。 |
| 10 | 它有外键的概念。 | 它没有外键的概念。 |