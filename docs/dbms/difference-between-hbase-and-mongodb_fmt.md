# HBase 和 MongoDB 的区别

> 原文: [https://www.geeksforgeeks.org/difference-between-hbase-and-mongodb/](https://www.geeksforgeeks.org/difference-between-hbase-and-mongodb/)

**1. HBase:**
`HBase` 是一个开源的、分布式的、面向列的数据库，建立在 `Hadoop` 文件系统之上。它用于提供对大量结构化数据的随机访问，数据存储在 `HDFS` 中，并提供数据复制功能。

**2. MongoDB:**
[`MongoDB`](https://www.geeksforgeeks.org/mongodb-an-introduction/) 是一个面向文档的数据库，不需要数据的行列格式。它提供高性能，本质上是动态的，不需要像传统的关系数据库管理系统那样预先定义模式。`MongoDB` 以 `JSON` 格式存储数据，这允许您以任何想要的形式发送数据。它是一个跨平台的数据库，几乎可以与 `Windows`、`Linux` 等所有平台协同工作。

## HBase 与 MongoDB 的区别

| 特性 | HBase | MongoDB |
| :--- | :--- | :--- |
| **数据模型** | 它是面向列的。 | 它是面向文档的。 |
| **开发语言** | 它是用 `Java` 写的。 | 它是用 `C`、`C++` 和 `Javascript` 编写的。 |
| **开发者** | 由 `Apache` 软件基金会开发。 | 由 `MongoDB` 公司开发。 |
| **触发器** | 它有触发器。 | 它也有触发器。 |
| **索引** | 它没有辅助索引。 | 它有二级索引。 |
| **复制** | 使用可选的复制因子。 | 使用主从复制因子。 |
| **数据存储** | 数据以键/值对的形式存储。 | 数据不以键/值对的形式存储。 |
| **操作延迟** | `HBase` 具有高延迟操作。 | `MongoDB` 具有低延迟操作。 |
| **数据类型** | `HBase` 用于存储结构化数据。 | `MongoDB` 用于存储任何类型的数据。 |
| **数据库架构** | 它有分布式数据库。 | 它有分散的数据库。 |
| **复杂性** | `HBase` 没有 `MongoDB` 复杂。 | 它比 `HBase` 更复杂。 |