# Adabas 和阿里巴巴云分析数据库对 PostgreSQL 的区别

> 原文：[https://www.geeksforgeeks.org/difference-between-adabas-and-alibaba-cloud-analyticdb-for-postgresql/](https://www.geeksforgeeks.org/difference-between-adabas-and-alibaba-cloud-analyticdb-for-postgresql/)

## 1. Adabas
`Adabas` 代表适应性数据库系统。它是由 Software AG 公司开发的，在 `IBM` 主机上运行。它于 1971 年推出。这是一个面向大型机和 `Linux/Unix/Windows` 环境的 `OLTP-DBMS`。`Adabas` 是一种企业数据库管理系统（`DBMS`），旨在实现可靠性、高性能、可扩展性和低总拥有成本。

## 2. 阿里巴巴云分析数据库 for PostgreSQL
分析数据库是阿里巴巴云上的一个在线分析处理数据库系统。它提供了 `PostgreSQL` 和 `MySQL` 两个版本。`PostgreSQL` 的 `AnalyticDB` 是基于 `Greenplum` 开源数据库程序的在线 `MPP`（大规模并行处理）数据仓库服务，并通过阿里巴巴云的一些深入扩展得到增强。

## Adabas 与阿里巴巴云 AnalyticDB for PostgreSQL 的区别

| 编号 | Adabas | 阿里巴巴云分析数据库 |
| :--- | :--- | :--- |
| 1. | 它是由 `Software AG` 公司在 1971 年开发的。 | 它由阿里巴巴、`Pivotal Software Inc.` 和 `PostgreSQL` 全球开发集团于 2016 年开发。 |
| 2. | 它是一个面向大型机和 `Linux/Unix/Windows` 环境的 `OLTP-DBMS`。 | 它是基于 `Greenplum` 的在线 `MPP`（大规模并行处理）数据仓库服务。 |
| 3. | 它不支持内存功能。 | 它也不支持内存功能。 |
| 4. | `Adabas` 的服务器操作系统有 `BS2000`、`Linux`、`Unix`、`Windows`、`z/OS` 和 `z/VSE`。 | 在阿里巴巴云分析数据库中，有托管服务器操作系统。 |
| 5. | 它不支持 `XML` 格式。 | 它支持 `XML` 格式。 |
| 6. | 服务器端脚本是用自然语言完成的。 | 它还支持服务器端脚本。 |
| 7. | 它支持分区方法。 | 支持的分区方法是分片。 |
| 8. | 它支持带有附加产品 `Adabas SQL Gateway` 的 `SQL` 查询语言。 | 还支持 `SQL` 查询语言。 |
| 9. | 它支持使用附加产品事件复制器进行复制。 | 它还支持复制方法。 |
| 10. | `Adabas` 没有提供参照完整性的概念。因此，没有外键。 | `PostgreSQL` 的 `AnalyticDB` 提供了引用完整性的概念。因此，有外键。 |
| 11. | `Adabas` 的许可证是商业的。 | 阿里巴巴云分析数据库 for `PostgreSQL` 的许可也是商业的。 |
| 12. | 主要的数据库模型是多值数据库管理系统。 | 主要的数据库模型是关系型数据库管理系统。 |
| 13. | 它没有为用户定义的映射/缩减方法提供任何应用编程接口。 | 它也没有为用户定义的映射/减少方法提供任何应用编程接口。 |