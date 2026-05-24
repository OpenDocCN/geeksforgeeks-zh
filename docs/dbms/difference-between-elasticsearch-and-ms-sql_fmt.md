# 弹性搜索和 MS SQL 的区别

> 原文：[https://www.geeksforgeeks.org/difference-between-elasticsearch-and-ms-sql/](https://www.geeksforgeeks.org/difference-between-elasticsearch-and-ms-sql/)

## 1. `Elasticsearch`
`Elasticsearch` 是一个分布式搜索和分析引擎。它是开源的，可以用于所有类型的数据。它是用 `Java` 编程语言实现的，支持所有有 `Java` 虚拟机的操作系统。它是 `Elastic Stack` 的主要组成部分，`Elastic Stack` 是一个用于数据分析和可视化的开源应用程序。它具有很高的可扩展性，并且执行动作的速度也很快，这使得它成为数据分析、处理和可视化的简单快捷的工具。

## 2. `MS SQL`
`MS SQL` 是微软于 1989 年开发的关系数据库管理系统。它是一个高度可扩展和安全的数据存储平台。它提供具有高性能和安全性的智能分析功能。[`MS SQL Server`](https://www.geeksforgeeks.org/introduction-of-ms-sql-server/) 的核心组件是控制数据及其处理的 `SQL Server` 数据库引擎。它支持 `ACID` 属性，并保证可靠地处理事务。

## 弹性搜索和 MS SQL 的区别

| 编号 | `Elasticsearch` | `MS SQL` |
| :--- | :--- | :--- |
| 1. | `Elasticsearch` 是一个基于 `Apache Lucene` 的搜索和分析引擎。 | `MS SQL` 是一个关系数据库模型。 |
| 2. | 主要的数据库模型是搜索引擎。 | 主数据库模型是一个关系模型。 |
| 3. | 它没有事务的概念。 | 它有满足 `ACID` 属性的事务的概念。 |
| 4. | 它是由 `ELASTIC` 在 2010 年开发的。 | 它是由微软在 1989 年开发的。 |
| 5. | 它支持所有带有 `Java` 虚拟机的操作系统。 | 它支持像 `Linux` 和 `Windows` 这样的操作系统。 |
| 6. | 它是一个开源软件。 | 它是一个商业软件。 |
| 7. | 它是用 `Java` 实现的。 | 它是用 `C++` 实现的。 |
| 8. | 在 `Elasticsearch` 中，分区是通过分片来完成的。 | 在 `MS SQL` 中分区是由水平分区完成的。 |
| 9. | 就排名而言，被认为不如 `MS SQL`。 | 就排名而言，它被认为比 `Elasticsearch` 更好。 |
| 10. | 它不使用外键。 | 它使用外键。 |