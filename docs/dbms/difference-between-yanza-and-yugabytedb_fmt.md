# 燕莎和 YugabyteDB 的区别

> 原文：[https://www.geeksforgeeks.org/difference-between-yanza-and-yugabytedb/](https://www.geeksforgeeks.org/difference-between-yanza-and-yugabytedb/)

## YugabyteDB
`YugabyteDB` 是开源、云原生和高性能的分布式 SQL 数据库，用于全球分布式文档存储。它旨在使应用变得敏捷。`YugabyteDB` 总部位于加利福尼亚州森尼维尔。`YugabyteDB` 是作为 `Apache 2.0` 开源项目分发和开发的。

## Yanza
`Yanza` 是由 `Yanza` 开发的[物联网](https://www.geeksforgeeks.org/introduction-to-internet-of-things-iot-set-1/)应用的时间序列数据库管理系统。它的服务器操作系统是 `Windows`，支持 `HTTP API`。

## Yanza 和 YugabyteDB 的区别

| No. | YugabyteDB | Yanza |
| :--- | :--- | :--- |
| 1 | 由 `Yugabyte Inc.` 开发，最初于 2017 年发布，目前于 2020 年 3 月发布。 | 由 `Yanza` 开发，最初于 2015 年发布。 |
| 2 | `YugabyteDB` 的服务器操作系统是 `Linux`，`OS X`。 | `Yanza` 的服务器操作系统是 `Windows`。 |
| 3 | 它的主要数据库模型是关系数据库管理系统。 | 它的主要数据库模型是时间序列数据库管理系统。 |
| 4 | 它支持 `C`、`C#`、`C++`、`Go`、`Java`、`JavaScript (Node.js)`、`Python`、`Ruby` 等编程语言。 | 它支持任何支持 `HTTP` 调用的语言。 |
| 5 | 它支持 `YCQL`，这是一个基于 `SQL` 的灵活模式应用编程接口，其根源在于 `Cassandra` 查询语言。 | 它支持 `HTTP API`。 |
| 6 | `YugabyteDB` 的数据方案取决于所使用的数据模型。 | `Yanza` 的数据方案是无模式的。 |
| 7 | 它支持类型索引和辅助索引。 | 它不支持类型索引和辅助索引。 |
| 8 | `YugabyteDB` 的实现语言是 `C` 和 `C++`。 | 它没有任何实现语言。 |
| 9 | 它在写入时具有很强的一致性，在读取时无法保持一致性。 | 它有立即一致性的概念。 |
| 10 | 它有外键。 | 它没有外键。 |