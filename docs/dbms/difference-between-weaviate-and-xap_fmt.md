# 威瓦特和 XAP 的区别

> 原文：[https://www.geeksforgeeks.org/difference-between-weaviate-and-xap/](https://www.geeksforgeeks.org/difference-between-weaviate-and-xap/)

**1.**
`Weaviate` 是一个基于开源 `GraphQL` 的智能图，具有语义搜索、自动分类和知识表示等核心功能。主数据库模型是搜索引擎，辅助数据库模型是图形数据库管理系统。

**2. XAP：**
`XAP` 是一个面向任务关键型应用的高性能内存数据网格。它提供了一组基本的数据存储功能，例如事务、索引和查询语言（类似于 `SQL` 的查询）。它是一种用于安装和分发应用软件的文件格式。

## 维阿蒂和 XAP 的区别：

| 编号 | Weaviate | XAP |
| :--- | :--- | :--- |
| 1. | 它由 `SeMI Technologies B.V.` 开发，最初于 2017 年发布。 | 它由 `Gigaspaces Technologies` 开发，最初于 2000 年发布。 |
| 2. | 它的主要数据库模型是搜索引擎。 | 它的主要数据库模型是文档存储和键值存储。 |
| 3. | 它的二级数据库模型是图形数据库管理系统。 | 它的二级数据库模型是面向对象的数据库管理系统。 |
| 4. | `Weaviate` 的实现语言是 `Go`。 | `XAP` 的实现语言是 `Java`、`.Net` 和 `C++`。 |
| 5. | `Weaviate` 的数据方案是映射到 `GraphQL` 接口。 | `XAP` 没有数据计划。 |
| 6. | `SQL-GraphQL` 被用作查询语言。 | `DML` 语句和类似 `SQL` 的查询语言。 |
| 7. | `Weaviate` 支持 `GraphQL` 查询语言和 `RESTful HTTP/JSON API`。 | `XAP` 支持 `gigaspace LRMI`、`Hibernate`、`JCache`、`JDBC`、`JPA`、`ODBC`、`RESTful HTTP API` 和 `Spring Data`。 |
| 8. | `Weaviate` 有最终一致性的概念。 | `XAP` 有即时一致性的概念。 |
| 9. | 缺少服务器端脚本和触发器。 | 服务器端脚本和触发器的存在。 |
| 10. | 它不包含事务概念。 | `XAP` 有 [`ACID`](https://www.geeksforgeeks.org/acid-properties-in-dbms/)（原子性、一致性、隔离性和持久性）事务概念。 |