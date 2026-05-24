# 卡珊德拉和 PostgreSQL 的区别

> 原文：[https://www.geeksforgeeks.org/difference-between-cassandra-and-postgresql/](https://www.geeksforgeeks.org/difference-between-cassandra-and-postgresql/)

## 1. [`卡珊德拉`](https://www.geeksforgeeks.org/apache-cassandra-nosql-database/)
[`卡珊德拉`](https://www.geeksforgeeks.org/apache-cassandra-nosql-database/)是一个免费开源的、分布式的、宽栏目的 [`NoSQL`](https://www.geeksforgeeks.org/introduction-to-nosql/) 数据库管理系统。它由 [`Apache`](https://www.geeksforgeeks.org/apache-cassandra-nosql-database/) 软件基金会开发，最初于 2008 年 7 月发布。[`Cassandra`](https://www.geeksforgeeks.org/apache-cassandra-nosql-database/) 旨在处理许多商用服务器上的大量数据，提供高可用性，没有单点故障。

## 2. [`PostgreSQL`](https://www.geeksforgeeks.org/python-database-management-in-postgresql/)
[`PostgreSQL`](https://www.geeksforgeeks.org/python-database-management-in-postgresql/) 是一个强大的开源对象关系数据库系统。由于其高稳定性，它以低维护工作量提供了良好的性能。[`PostgreSQL`](https://www.geeksforgeeks.org/python-database-management-in-postgresql/) 是第一个实现多版本并发控制([`MVCC`](https://www.geeksforgeeks.org/python-database-management-in-postgresql/))功能的数据库管理系统。

## 卡珊德拉和波斯特格雷的区别

| 没有 | 凶事预言家 | 一种数据库系统 |
| --- | --- | --- |
| 1. | 由 [`Apache`](https://www.geeksforgeeks.org/apache-cassandra-nosql-database/) 软件基金会开发，于 2008 年 7 月发布。 | 由 [`PostgreSQL`](https://www.geeksforgeeks.org/python-database-management-in-postgresql/) 全球开发小组于 1989 年开发。 |
| 2. | 它是基于 [`BigTable`](https://www.geeksforgeeks.org/difference-between-cassandra-and-postgresql/) 和 [`DynamoDB`](https://www.geeksforgeeks.org/difference-between-cassandra-and-postgresql/) 思想的宽栏商店。 | 它是广泛使用的开源 [`RDBMS`](https://www.geeksforgeeks.org/difference-between-cassandra-and-postgresql/)。 |
| 3. | [`Cassandra`](https://www.geeksforgeeks.org/apache-cassandra-nosql-database/) 是用 [`Java`](https://www.geeksforgeeks.org/difference-between-cassandra-and-postgresql/) 语言编写的。 | [`PostgreSQL`](https://www.geeksforgeeks.org/python-database-management-in-postgresql/) 是用 [`C`](https://www.geeksforgeeks.org/difference-between-cassandra-and-postgresql/) 语言编写的。 |
| 4. | [`卡珊德拉`](https://www.geeksforgeeks.org/apache-cassandra-nosql-database/)的主要数据库模型是宽列存储。 | [`PostgreSQL`](https://www.geeksforgeeks.org/python-database-management-in-postgresql/)的主要数据库模型是关系数据库管理系统。 |
| 5. | 它没有辅助数据库模型。 | 它将文档存储为辅助数据库模型。 |
| 6. | [`卡珊德拉`](https://www.geeksforgeeks.org/apache-cassandra-nosql-database/)的服务器操作系统是 [`BSD`](https://www.geeksforgeeks.org/difference-between-cassandra-and-postgresql/)、[`Linux`](https://www.geeksforgeeks.org/difference-between-cassandra-and-postgresql/)、[`OS X`](https://www.geeksforgeeks.org/difference-between-cassandra-and-postgresql/) 和 [`Windows`](https://www.geeksforgeeks.org/difference-between-cassandra-and-postgresql/)。 | [`PostgreSQL`](https://www.geeksforgeeks.org/python-database-management-in-postgresql/)的服务器操作系统有 [`FreeBSD`](https://www.geeksforgeeks.org/difference-between-cassandra-and-postgresql/)、[`惠普-UX`](https://www.geeksforgeeks.org/difference-between-cassandra-and-postgresql/)、[`Linux`](https://www.geeksforgeeks.org/difference-between-cassandra-and-postgresql/)、[`NetBSD`](https://www.geeksforgeeks.org/difference-between-cassandra-and-postgresql/)、[`OpenBSD`](https://www.geeksforgeeks.org/difference-between-cassandra-and-postgresql/)、[`OS X`](https://www.geeksforgeeks.org/difference-between-cassandra-and-postgresql/)、[`Solaris`](https://www.geeksforgeeks.org/difference-between-cassandra-and-postgresql/)、[`Unix`](https://www.geeksforgeeks.org/difference-between-cassandra-and-postgresql/) 和 [`Windows`](https://www.geeksforgeeks.org/difference-between-cassandra-and-postgresql/)。 |
| 7. | 它不支持 [`XML`](https://www.geeksforgeeks.org/difference-between-cassandra-and-postgresql/) 格式。 | 它支持 [`XML`](https://www.geeksforgeeks.org/difference-between-cassandra-and-postgresql/) 格式。 |
| 8. | 它支持二级索引，但方式有限，即仅支持相等查询，并不总是性能最佳的解决方案。 | 它支持二级索引。 |
| 9. | 它不支持服务器端脚本。 | 它有用户定义的服务器端脚本函数。 |
| 10. | 它支持可选择的复制因子方法。 | 它支持主-主复制方法。 |
| 11. | 在 [`Cassandra`](https://www.geeksforgeeks.org/apache-cassandra-nosql-database/) 中，分区可以通过分片来完成。 | 在 [`PostgreSQL`](https://www.geeksforgeeks.org/python-database-management-in-postgresql/) 中，分区可以通过范围、列表和散列来完成。 |
| 12. | 它为用户定义的映射/缩减方法提供了一个应用编程接口。 | 它没有为用户定义的映射/缩减方法提供应用编程接口。 |
| 13. | [`卡珊德拉`](https://www.geeksforgeeks.org/apache-cassandra-nosql-database/)没有提供参照完整性的概念。因此，没有外键。 | [`PostgreSQL`](https://www.geeksforgeeks.org/python-database-management-in-postgresql/)提供了引用完整性的概念，并且具有外键。 |