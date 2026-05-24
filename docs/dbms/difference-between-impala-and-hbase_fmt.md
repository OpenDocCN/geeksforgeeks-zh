# Impala 与 HBase 的区别

> 原文：[https://www.geeksforgeeks.org/difference-between-impala-and-hbase/](https://www.geeksforgeeks.org/difference-between-impala-and-hbase/)

## 1. Impala
`Impala` 是一个运行在 `Hadoop` 上的查询引擎。它对存储在 `Hadoop` 中的数据提供高性能、低延迟的 `SQL` 查询。它是一个开源软件。它支持内存中的数据处理。它率先使用了 `Parquet` 文件格式，这是一种列式存储布局，针对数据仓库场景中典型的大规模查询进行了优化。

## 2. HBase
该模型用于提供对大量结构化数据的随机访问。它建立在 `Hadoop` 文件系统之上，本质上是面向列的。它曾经在 `HDFS` 存储数据。它是提供数据复制的开源数据库。

## Impala 与 HBase 的区别

| 序列号 | Impala | HBase |
| :--- | :--- | :--- |
| 1. | 它是由 `Cloudera` 开发的。 | 由 `Apache` 软件基金会开发。 |
| 2. | `Impala` 于 2013 年发布 | `HBase` 于 2008 年发布 |
| 3. | `Impala` 是用 `C++` 实现的程序设计语言 | `HBase` 是使用 `Java` 实现的程序设计语言 |
| 4. | `Linux` 是唯一使用 `Impala` 的服务器操作系统。 | `Linux`、`Unix` 和 `Windows` 都是使用 `HBase` 的服务器操作系统。 |
| 5. | 它支持诸如 `DML` 和 `DDL` 语句之类的 `SQL`。 | 它不支持 `SQL`（标准查询语言）。 |
| 6. | 触发器不在 `Impala` 中使用 | 触发器用于 `HBase` |
| 7. | `JDBC` 和 `ODBC` 是 `Impala` 中使用的 `API` 和访问方法。 | `Java API`、`RESTful HTTP API`、`Thrift` 是 `HBase` 中使用的 `API` 和访问方法。 |
| 8. | `Impala` 中使用的复制方法是可选择的复制因子。 | `HBase` 中使用的复制方法有主-主复制和主从复制。 |