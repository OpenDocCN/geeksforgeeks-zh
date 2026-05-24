# 亚马逊极光和亚马逊 DynamoDB 的区别

> 原文：[https://www.geeksforgeeks.org/difference-between-amazon-aurora-and-amazon-dynamodb/](https://www.geeksforgeeks.org/difference-between-amazon-aurora-and-amazon-dynamodb/)

## 1. `Amazon Aurora`
`Amazon Aurora` 是来自 `Amazon Web Services` 的全托管关系数据库引擎，与 `MySQL` 和 `PostgreSQL` 兼容。它比标准的 `MySQL` 数据库快大约 5 倍，比标准的 `PostgreSQL` 数据库快 3 倍。`Aurora` 的特点是分布式容错和自愈存储系统。

## 2. `Amazon DynamoDB`
`Amazon DynamoDB` 是一个完全管理的数据库，支持文档和键值数据模型。特点如下——快速灵活的 `NoSQL` 数据库服务，适用于任何规模的需要一致的一位数毫秒延迟的所有应用程序。它是由 `Amazon` 托管的、可扩展的数据库服务，数据存储在 `Amazon` 云中。

## `Amazon Aurora` 和 `Amazon DynamoDB` 的区别

| 没有。 | `Amazon Aurora` | `Amazon DynamoDB` |
| --- | --- | --- |
| 1. | 它是 `Amazon` 在 2015 年开发的。 | 它是 `Amazon` 在 2012 年开发的。 |
| 2. | 是 `Amazon` 提供的 `MySQL` 和 `PostgreSQL` 兼容的云服务。 | 它是由 `Amazon` 托管的、可扩展的数据库服务，数据存储在 `Amazon` 云中。 |
| 3. | 它提供了参照完整性的概念。因此，没有外键。 | 它没有提供参照完整性的概念。因此，没有外键。 |
| 4. | 即时一致性用于确保分布式系统中的一致性。 | 最终一致性和即时一致性用于确保分布式系统中的一致性。 |
| 5. | 它的主要数据库模型是关系数据库管理系统。 | 它的主要数据库模型是文档存储和键值存储。 |
| 6. | 它支持服务器端脚本。 | 它不支持服务器端脚本。 |
| 7. | 分区可以通过水平分区来完成。 | 它支持分片作为分区方法。 |
| 8. | 它支持 `SQL` 查询语言。 | 它不支持 `SQL` 查询语言。 |
| 9. | 它只支持一种复制方法——主从复制。 | 它支持复制方法。 |
| 10. | 它没有为用户定义的映射/缩减方法提供应用编程接口。 | 它没有为用户定义的映射/缩减方法提供应用编程接口。但也许可以通过 `Amazon Elastic MapReduce` 来实现。 |