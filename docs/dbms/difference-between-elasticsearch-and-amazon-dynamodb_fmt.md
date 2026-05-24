# Elasticsearch 和 Amazon DynamoDB 的区别

> 原文: [https://www.geeksforgeeks.org/difference-between-elasticsearch-and-amazon-dynamodb/](https://www.geeksforgeeks.org/difference-between-elasticsearch-and-amazon-dynamodb/)

## 介绍

`Elasticsearch` 是一个分布式搜索和分析引擎。它是开源的，可以用于所有类型的数据。它是用 `Java` 编程语言实现的，支持所有有 `Java` 虚拟机的操作系统。它是 `Elastic Stack` 的主要组成部分，`Elastic Stack` 是一个用于数据分析和可视化的开源应用程序。它具有很高的可扩展性，并且执行动作的速度也很快，这使得它成为数据分析、处理和可视化的简单快捷的工具。

`Amazon DynamoDB` 是一个可扩展性很高的文档数据库。是亚马逊在 2012 年给的。它有一个作为文档存储和键值存储的主数据库模型。它有商业许可证。它使用事务并遵循 `ACID` 属性。有备份设施，安全性高。`Amazon DynamoDB` 是一个持久耐用的数据库。它可以在一天内处理大量的请求，并且得到了充分的管理。

## 对比

| 没有 | `Elasticsearch` | `Amazon DynamoDB` |
| --- | --- | --- |
| 1. | `Elasticsearch` 是一个基于 `Apache Lucene` 的搜索和分析引擎。 | `Amazon DynamoDB` 是一个可扩展的数据库，数据存储在亚马逊云上。 |
| 2. | 主要的数据库模型是搜索引擎。 | 主要的数据库模型是 `Amazon DynamoDB` 中的文档存储和键值存储。 |
| 3. | 它没有交易的概念。 | 它有满足 `ACID` 属性的事务的概念。 |
| 4. | 它是由 `ELASTIC` 在 2010 年开发的。 | 它是亚马逊在 2012 年开发的。 |
| 5. | 它支持所有带有 `Java` 虚拟机的操作系统。 | 它支持托管操作系统。 |
| 6. | 它是一个开源软件。 | 它是一个商业软件。 |
| 7. | 它是用 `Java` 实现的。 | 它没有 `Java` 作为实现语言。 |
| 8. | 它不是基于云的。 | 它基于云。 |
| 9. | 就排名而言，它被认为比亚马逊 `DynamoDB` 更好。 | 就排名而言，它被认为不如 `Elasticsearch`。 |
| 10. | 它有服务器端脚本。 | 它没有服务器端脚本。 |