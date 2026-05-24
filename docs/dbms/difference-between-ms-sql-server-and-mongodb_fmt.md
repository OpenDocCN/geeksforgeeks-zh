# MS SQL Server 与 MongoDB 的区别

> 原文：[`https://www.geeksforgeeks.org/difference-between-ms-sql-server-and-mongodb/`](https://www.geeksforgeeks.org/difference-between-ms-sql-server-and-mongodb/)

## MS SQL Server
微软 SQL Server 是一个依赖于平台的关系数据库管理系统（RDBMS），它既是 GUI 也是基于命令的软件。它支持企业信息技术环境中的各种交易处理、商业智能和分析应用。它由微软公司开发，最初于 1989 年 4 月 24 日发布。用 [`C`](https://www.geeksforgeeks.org/c-programming-language/) 和 [`C++`](https://www.geeksforgeeks.org/c-plus-plus/) 语言编写。

## MongoDB
MongoDB 是一个面向跨平台文档的非关系型（即 [`NoSQL`](https://www.geeksforgeeks.org/introduction-to-nosql/)）数据库程序。它是一个开源文档数据库，以键值对的形式存储数据。MongoDB 由 MongoDB Inc. 开发，最初于 2009 年 2 月 11 日发布。用 [`C++`](https://www.geeksforgeeks.org/c-plus-plus/)、[`Go`](https://www.geeksforgeeks.org/go-programming-language-introduction/)、[`JavaScript`](https://www.geeksforgeeks.org/javascript-tutorial/)、[`Python`](https://www.geeksforgeeks.org/python-programming-language/) 语言编写。MongoDB 提供了高速度、高可用性和高扩展性。

### MS SQL Server 与 MongoDB 的区别

```
| 编号 | MS SQL Server | MongoDB |
| --- | --- | --- |
| 1. | 由微软公司开发，最初于 1989 年 4 月 24 日发布。 | 由 MongoDB Inc. 开发，最初于 2009 年 2 月 11 日发布。 |
| 2. | 用 `C` 和 `C++` 编写。 | 用 `C++`、`Go`、`JavaScript`、`Python` 语言编写。 |
| 3. | 主要数据库模型是 `关系数据库管理系统`。 | 主要数据库模型是 `文档存储`。 |
| 4. | 许可证是商业的。 | 许可证是开源的。 |
| 5. | 支持 `XML` 数据格式。 | 不支持 `XML` 数据格式。 |
| 6. | 提供无快照隔离的 `ACID` 事务。 | 为多文档 `ACID` 事务提供快照隔离。 |
| 7. | 数据模式是固定的。 | 数据模式是动态的。 |
| 8. | 提供了引用完整性的概念，并且有外键。 | 没有提供引用完整性的概念，因此没有外键。 |
| 9. | 不支持 `MapReduce` 方法。 | 支持 `MapReduce` 方法。 |
| 10. | 服务器操作系统是 `Linux`、`Windows`。 | 服务器操作系统有 `Solaris`、`Linux`、`OS X`、`Windows`。 |
| 11. | 花旗、美国银行、UPS 等知名公司使用。 | Adobe、Amadeus、Lyft、ViaVarejo、Craftbase 等知名公司使用。 |
```