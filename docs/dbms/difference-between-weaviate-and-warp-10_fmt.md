# Weaviate和Warp 10的区别

> 原文：[https://www.geeksforgeeks.org/difference-between-weaviate-and-warp-10/](https://www.geeksforgeeks.org/difference-between-weaviate-and-warp-10/)

## Weaviate

它是基于开源`GraphQL`的智能图，具有核心特性：语义搜索、自动分类和知识表示。主数据库模型是搜索引擎，辅助数据库模型是图形数据库管理系统。它允许我们的数据以基于`GraphQL`查询语言的大型图形格式表示。它的搜索图基于一种叫做`Contextionary`的图嵌入机制。

## Warp 10

它是一个时间序列数据库管理系统，专门处理基于`LevelDB`或`HBase`的带时间戳的地理数据。Warp 10的服务器操作系统是`Linux`、`OS X`、`Windows`。它是最先进的时间序列平台。Warp 10是一个开源地理时间序列平台，旨在监控系统和物联网，并处理来自传感器的数据。

## 对比表格

```
| 编号 | Weaviate | Warp 10 |
| :--- | :--- | :--- |
| 1 | 它由`SeMI Technologies B.V.`开发，最初于2017年发布，目前于2020年1月发布。 | 它由`SenX`开发，最初于2015年发布。 |
| 2 | 它的主要数据库模型是搜索引擎。 | 它的主要数据库模型是时间序列数据库管理系统。 |
| 3 | 二级数据库模型是图形数据库管理系统。 | 缺少辅助数据库模型。 |
| 4 | 它支持`GraphQL`查询语言和`RESTful` `HTTP`/`JSON` API。 | 它支持`HTTP` API、`Jupyter`、`WebSocket`。 |
| 5 | Weaviate的数据方案是映射到`GraphQL`接口。 | 它具有无模式数据方案。 |
| 6 | 它有最终一致性的概念。 | 它有立即一致性的概念。 |
| 7 | 它包含分片分区方法。 | Warp 10支持分片分区方法。 |
| 8 | `GraphQL`被用作查询语言。 | 没有这样的`SQL`。 |
| 9 | 它的实现语言是`Go`。 | 它的实现语言是`Java`。 |
```