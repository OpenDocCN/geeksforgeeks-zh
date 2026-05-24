# 甲骨文与 Couchbase 的区别

> 原文：[https://www.geeksforgeeks.org/difference-between-oracle-and-couchbase/](https://www.geeksforgeeks.org/difference-between-oracle-and-couchbase/)

## 1. 甲骨文

甲骨文是一个关系数据库管理系统（`RDBMS`）。它是由甲骨文公司在 1980 年开发的。它是第一个为网格计算设计的数据库，为管理信息和应用程序提供了最灵活和最经济的方式。它运行在主要平台上，如视窗、Unix、Linux 和 macOS。它是一个关系数据库，用户通过名为 `SQL` 的应用程序或查询语言来访问其中的数据。

## 2. Couchbase

Couchbase Server 是一款开源、分布式多模型 `NoSQL` 面向文档的数据库软件包，针对交互应用进行了优化。它也被称为 Membase。它由 Couchbase，Inc. 开发，最初于 2010 年 8 月发布。

## 甲骨文与 Couchbase 的区别

| 序号 | 甲骨文 | Couchbase |
| :--- | :--- | :--- |
| 1. | 它是由甲骨文公司在 1980 年开发的。 | 它由 Couchbase，Inc. 开发，最初于 2010 年 8 月发布。 |
| 2. | 是用 `C`、`C++` 写的。 | 用 `C++`、`Erlang`、`C`、`Go` 语言编写。 |
| 3. | 它是一个商业软件。 | 它是一个开源软件。 |
| 4. | 甲骨文的服务器操作系统有 Solaris、Linux、OS X、Windows。 | Couchbase 的服务器操作系统是 Linux、OS X 和 Windows。 |
| 5. | 主要的数据库模型是关系数据库管理系统。 | Couchbase 的主要数据库模型是文档存储。 |
| 6. | 它使用水平分区方法在不同的节点上存储不同的数据。 | 它使用分片分区方法在不同的节点上存储不同的数据。 |
| 7. | 即时一致性方法确保一致性。 | 最终一致性和即时一致性方法确保分布式系统中的一致性。 |
| 8. | 它根据 `SQL` 标准提供细粒度的访问权限。 | 它通过基于密码和 `LDAP` 集成的身份验证，实现了用户和管理员的分离。 |
| 9. | 使用交易的 `ACID` 属性。 | 它还提供 `ACID` 事务。 |
| 10. | Oracle 支持的复制方式有主从复制，主-主复制。 | Couchbase 支持的复制方法还有主从复制、主-主复制。 |