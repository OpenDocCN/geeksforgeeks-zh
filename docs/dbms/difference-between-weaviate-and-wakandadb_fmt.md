# 威瓦特和瓦坎达布的区别

> 原文：[https://www.geeksforgeeks.org/difference-between-weaviate-and-wakandadb/](https://www.geeksforgeeks.org/difference-between-weaviate-and-wakandadb/)

## 1. Weaviate

Weaviate 是一个基于开源 `GraphQL` 的智能图，其核心特征是：语义搜索、自动分类和知识表示。主数据库模型是搜索引擎，次数据库模型是图形数据库管理系统。它允许我们的数据以基于 `GraphQL` 查询语言的大型图形格式表示。它的搜索图基于一种叫做 `Contextionary` 的图嵌入机制。

## 2. WakandaDB

WakandaDB 是一个服务器端 `JavaScript` 引擎，用来访问数据并嵌入到提供 `REST API` 的服务器中。WakandaDB 的主要数据库模型是面向对象的数据库管理系统。WakandaDB 是一个开发和运行网络或移动应用的 `JavaScript` 平台，通过 `HTTP` 访问 `NoSQL` 引擎。

## 威瓦特和瓦坎达布的区别

| 编号 | Weaviate | WakandaDB |
| :--- | :--- | :--- |
| 1 | 由 `SeMI Technologies B.V.` 开发，最初于 2017 年发布，目前于 2020 年 1 月发布。 | 由 `Wakanda SAS` 开发，最初于 2012 年发布，目前于 2017 年 7 月发布。 |
| 2 | 它的主要数据库模型是搜索引擎，其辅助数据库模型是图形数据库管理系统。 | 它的主要数据库模型是面向对象的数据库管理系统。 |
| 3 | `Weaviate` 没有这样的服务器操作系统。 | `WakandaDB` 的服务器操作系统是 `Linux`、`OS X`、`Windows`。 |
| 4 | `Weaviate` 支持 `GraphQL` 查询语言和 `RESTful HTTP/JSON API`。 | 它支持 `RESTful HTTP API`。 |
| 5 | `Weaviate` 中事务概念的缺失。 | 它的事务概念是 `ACID`（原子性、一致性、隔离性和持久性）。 |
| 6 | 还有复制方法。 | 没有复制方法。 |
| 7 | `Weaviate` 的分割方法是碎片化。 | 它不支持分片分区方法。 |
| 8 | 在 `Weaviate` 中没有这种受支持的编程语言。 | 它支持 `JavaScript` 编程语言。 |
| 9 | 它有最终一致性的概念。 | `WakandaDB` 具有即时一致性。 |
| 10 | `Weaviate` 的实现语言是 `Go`。 | `WakandaDB` 的实现语言是 `C++`、`JavaScript`。 |