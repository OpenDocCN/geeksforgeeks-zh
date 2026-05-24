# RDBMS 和 Couchbase 的区别

> 原文: [https://www.geeksforgeeks.org/difference-between-rdbms-and-couchbase/](https://www.geeksforgeeks.org/difference-between-rdbms-and-couchbase/)

## 1. `RDBMS`
`RDBMS` 代表关系数据库管理系统。它是最受欢迎的数据库。在它中，数据以元组形式的行的形式存储。它包含大量的表和数据，因为数据存储在表中，所以很容易访问。该模型是由英菲尼提出的。

## 2. `Couchbase`
`Couchbase Server` 是一个开源的、分布式的、面向 `NoSQL` 文档的数据库软件包，针对交互式应用程序进行了优化。它也被称为 `Membase`。它由 `Couchbase, Inc.` 开发，最初于 2010 年 8 月发布。

## `RDBMS` 和 `Couchbase` 的区别

| 编号 | `RDBMS` | `Couchbase` |
| :--- | :--- | :--- |
| 1. | `RDBMS` 是一个关系数据库。 | 它是非关系型和面向文档的数据库。 |
| 2. | `RDBMS` 是基于列的。 | `Couchbase` 是基于文档的。 |
| 3. | 它有一个预定义的模式。 | 它有一个动态模式。 |
| 4. | 它比 `Couchbase` 慢。 | `Couchbase` 比 `RDBMS` 快。 |
| 5. | 它只支持 `SQL` 查询语言。 | 它支持 `JSON` 查询语言。 |
| 6. | `RDBMS` 不提供用于查询的 `JavaScript` 客户端。 | 它提供了一个用于查询的 `JavaScript` 客户端。 |
| 7. | `RDBMS` 不适合分层数据存储。 | `Couchbase` 适用于分层数据存储。 |
| 8. | 它围绕着 `ACID` 属性。 | 它也围绕着 `ACID` 属性。 |
| 9. | `RDBMS` 是可垂直扩展的。 | `Couchbase` 可横向扩展。 |
| 10. | 它支持复杂的连接。 | 它不支持复杂的连接。 |