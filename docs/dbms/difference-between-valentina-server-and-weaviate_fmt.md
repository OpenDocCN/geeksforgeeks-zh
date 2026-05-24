# Valentina 服务器和 Weaviate 的区别

> 原文：[https://www.geeksforgeeks.org/difference-between-valentina-server-and-weaviate/](https://www.geeksforgeeks.org/difference-between-valentina-server-and-weaviate/)

## 1. 瓦伦蒂娜服务器
它是一个对象关系数据库和报表服务器以及快速对象关系数据库服务器。它包括集成数据库服务器，瓦伦蒂娜数据库服务器和 `SQLite` 数据库服务器。它是一个功能齐全、符合标准的基于 `SQLite` 的多用户访问数据库服务器。

## 2. Weaviate
这是一个开源的基于 `GraphQL` 的智能图，其核心特征是：语义搜索、自动分类和知识表示。主数据库模型是搜索引擎，辅助数据库模型是图形数据库管理系统。它允许我们的数据以基于 `GraphQL` 查询语言的大型图形格式表示。它的搜索图基于一种叫做 `Contextionary` 的图嵌入机制。

## Valentina Server 与 Weaviate 的区别

| 编号 | Valentina Server | Weaviate |
| :--- | :--- | :--- |
| 1 | 由 `Paradigma` 软件开发，最初于 1994 年发布。 | `SeMI Technologies B.V.` 开发，最初于 2017 年发布。 |
| 2 | `Valentina Server` 的当前版本是 5.7.5。 | 目前发布于 2020 年 1 月。 |
| 3 | `Valentina Server` 的服务器操作系统是 `Linux`、`OS X`、`Windows`。 | `Weaviate` 没有这样的服务器操作系统。 |
| 4 | 它的主要数据库模型是关系数据库管理系统。 | 它的主要数据库模型是搜索引擎，辅助数据库模型是图形数据库管理系统。 |
| 5 | `Valentina Server` 支持 `.Net`、`C`、`C#`、`C++`、`Objective-C`、`PHP`、`Ruby`、`Visual Basic`、`Visual Basic.NET` 编程语言。 | 在 `Weaviate` 中没有这种受支持的编程语言。 |
| 6 | `Valentina Server` 的 `API` 等访问方式是 `ODBC`。 | `Weaviate` 支持 `GraphQL` 查询语言和 `RESTful HTTP/JSON API`。 |
| 7 | 是的，`Valentina Server` 有一个数据模式。 | `Weaviate` 的数据模式是基于到 `GraphQL` 接口的映射。 |
| 8 | 它没有实现语言——`C#`。 | `Weaviate` 的实现语言是 `Go`。 |
| 9 | `Valentina Server` 中缺少事务概念。 | `Weaviate` 中交易概念的缺失。 |
| 10 | `Valentina Server` 没有一致性概念。 | 它有最终一致性的概念。 |
| 11 | 是的，它有外键。 | 它没有外键。 |
| 12 | `Valentina Server` 中缺少复制方法。 | `Weaviate` 的复制方法是主从复制和主从复制。 |
| 13 | `Valentina Server` 中缺少分区方法。 | `Weaviate` 的分割方法是碎片化。 |