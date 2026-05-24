# Virtuoso 与 YugabyteDB 的区别

> 原文：[https://www.geeksforgeeks.org/difference-between-virtuoso-and-yugabytedb/](https://www.geeksforgeeks.org/difference-between-virtuoso-and-yugabytedb/)

它是一个中间件，支持对表示为关系表和/或属性图的数据进行管理。它有多模型混合关系数据库管理系统，主要的数据库模型有图形数据库管理系统、原生 XML 数据库管理系统、关系数据库管理系统、RDF 存储、搜索引擎。专为利用操作系统线程支持和多个 CPU 而设计。它是一个支持实体完整性和引用完整性的对象关系数据库。

这是一个高性能、开源和云原生的分布式 SQL 数据库全球分布式文档存储。`YugabyteDB` 的目标是让应用变得敏捷。`YugabyteDB` 总部位于加利福尼亚州森尼维尔。它是作为 `Apache 2.0` 开源项目分发和开发的。

| 编号 | Virtuoso | YugabyteDB |
| :--- | :--- | :--- |
| 1 | 它由 `Virtuoso` 开发，最初于 1998 年发布，目前于 2019 年 5 月发布。 | 它由 `Yugabyte Inc.` 开发，最初于 2017 年发布，目前于 2020 年 3 月发布。 |
| 2 | 主要的数据库模型是图形数据库管理系统、原生 XML 数据库管理系统、关系数据库管理系统、RDF 存储、搜索引擎。 | 主要的数据库模型是关系数据库管理系统。 |
| 3 | 辅助数据库模型是文档存储。 | 辅助数据库模型是文档存储和宽列存储。 |
| 4 | `Virtuoso` 的实现语言是 `C`。 | `YugabyteDB` 的实现语言是 `C` 和 `C++`。 |
| 5 | 其服务器操作系统的 `Virtuoso` 是 `AIX`，`FreeBSD`，`HP-UX`，`Linux`，`OS X`，`Solaris`，`Windows`。 | `Linux`、`OS X` 都是 `YugabyteDB` 的服务器操作系统。 |
| 6 | `Virtuoso` 支持 `.Net`、`C`、`C#`、`C++`、`Java`、`JavaScript`、`Perl`、`PHP`、`Python`、`Ruby`、`Visual Basic` 编程语言。 | `YugabyteDB` 支持 `C`、`C#`、`C++`、`Go`、`Java`、`JavaScript (Node.js)`、`Python`、`Ruby` 等编程语言。 |
| 7 | `Virtuoso` 的复制方法基于链式、星型和双向复制，主-主复制，主从复制。 | 复制方法基于 `Raft` 分布式共识协议，最少 3 个副本以实现连续可用性。 |
| 8 | `Virtuoso` 有即时一致性的概念。 | 具有很强的写入一致性和可调的读取一致性。 |
| 9 | `ACID`（原子性、一致性、隔离性和持久性）是 `Virtuoso` 的事务概念。 | 事务概念是具有可序列化和快照隔离的分布式 `ACID`。灵感来自谷歌 `Spanner` 架构。 |