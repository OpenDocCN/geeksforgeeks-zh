# Transbase 和 Yanza 的区别

> 原文: [https://www.geeksforgeeks.org/difference-between-transbase-and-yanza/](https://www.geeksforgeeks.org/difference-between-transbase-and-yanza/)

## 1. Transbase
这是一个资源优化、高性能、普遍适用的关系数据库管理系统，由慕尼黑交易软件有限公司开发和维护。它是一个关系数据库管理系统，支持 SQL 标准的所有重要功能。`Transbase` 的数据库可通过附加函数进行扩展，自定义数据类型也通过动态多线程技术提供查询的并行执行。

## 2. Yanza
是 `Yanza` 为[物联网](https://www.geeksforgeeks.org/introduction-to-internet-of-things-iot-set-1/)应用开发的时间序列数据库管理系统。它的服务器操作系统是 `Window`，支持 `HTTP API`。

## Transbase 和 Yanza 的区别

| 编号 | Transbase | Yanza |
| :--- | :--- | :--- |
| 1 | 由交易软件有限公司开发，最初于 1987 年发布，目前于 2019 年 9 月发布。 | 由 `Yanza` 开发，最初于 2015 年发布。 |
| 2 | `FreeBSD`、`Linux`、`macOS`、`Solaris`、`Windows`，都是 `Transbase` 的服务器操作系统。 | `Windows` 是 `Yanza` 的服务器操作系统。 |
| 3 | 主要的数据库模型是`关系数据库管理系统`。 | 主要的数据库模型是`时间序列数据库管理系统`。 |
| 4 | 支持 `C`，`C#`，`C++`，`Java`，`JavaScript`，`Kotlin`，`Objective-C`，`PHP`，`Python` 都是编程语言。 | `Yanza` 支持任何支持 `HTTP` 调用的语言。 |
| 5 | `ADO.NET`、`JDBC`、`ODBC`、专有原生 `API` 是 `Transbase` 的 `API` 和其他访问方法。 | `YCQL`，一个基于 `SQL` 的灵活模式应用编程接口，其根源在于卡珊德拉查询语言、应用编程接口和其他访问方法。 |
| 6 | 是的，`Transbase` 有数据模式。 | `Yanza` 的数据方案是无模式的。 |
| 7 | 它有实现语言 `C` 和 `C++`。 | 它没有任何实现语言。 |
| 8 | 是的，`Transbase` 有交易概念。 | 它不包含事务概念。 |
| 9 | `Transbase` 的复制方法是主从复制。 | `Yanza` 缺少复制方法。 |
| 10 | `Transbase` 持有即时一致性概念。 | `Yanza` 有立即一致性的概念。 |
| 11 | 是的，它有外键。 | 不，它没有外键。 |