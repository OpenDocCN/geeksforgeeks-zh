# ActivePivot 和亚马逊海王星的区别

> 原文：[https://www.geeksforgeeks.org/difference-between-activepivot-and-amazon-neptune/](https://www.geeksforgeeks.org/difference-between-activepivot-and-amazon-neptune/)

## 1. ActivePivot
`ActivePivot` 是一个内存中的数据库管理系统，结合了事务和分析处理来处理不断变化的数据的聚合。该数据库使用列存储架构以及字典压缩和 `Java` 对象的二进制表示。它是法国公司 `ActiveViam` 的核心产品之一，该公司成立于 2005 年，曾被称为 `Quadra FS`。

## 2. 亚马逊海王星
亚马逊海王星是一个快速、可靠的图形数据库，由 `Amazon.com` 为云产品构建。它是亚马逊网络服务（`AWS`）的一部分，于 2017 年 11 月 29 日公布。它支持开源的 `Apache TinkerPop Gremlin` 图遍历语言。它允许用户使用通过 `AWS Key Management Service` 创建的密钥来加密数据库。

## 主动枢轴和亚马逊海王星的区别

| 编号 | ActivePivot | 亚马逊海王星 |
| :--- | :--- | :--- |
| 1. | 由 `ActiveViam` 开发。 | 由亚马逊于 2017 年开发。 |
| 2. | 它是一个内存中的数据库管理系统，结合了事务处理和分析处理来处理不断变化的数据的聚合。 | 这是一个由 `Amazon.com` 为云产品构建的快速、可靠的图形数据库。 |
| 3. | `ActivePivot` 的许可证是商业的。 | 亚马逊海王星的许可证是商业的。 |
| 4. | 它不能作为云服务使用。 | 它可以作为云服务使用。 |
| 5. | 它的主要数据库模型是面向对象的数据库管理系统。 | 它的主要数据库模型是图形数据库管理系统和 `RDF` 存储。 |
| 6. | 它支持服务器端脚本和 `Java` 中的后处理器。 | 它不支持服务器端脚本。 |
| 7. | 在 `ActivePivot` 中，分区可以通过分片和水平分区来完成。 | 它不支持分区方法。 |
| 8. | 它支持带有多维表达式的 `SQL` 查询语言。 | 它不支持 `SQL` 查询语言。 |
| 9. | 它不支持任何复制方法。 | 它支持多可用性区域高可用性。 |