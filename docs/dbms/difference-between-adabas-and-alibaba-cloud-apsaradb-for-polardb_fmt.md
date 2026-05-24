# Adabas 与阿里巴巴云 ApsaraDB for PolarDB 的区别

> 原文：[https://www.geeksforgeeks.org/difference-between-adabas-and-alibaba-cloud-apsaradb-for-polardb/](https://www.geeksforgeeks.org/difference-between-adabas-and-alibaba-cloud-apsaradb-for-polardb/)

## 1. Adabas
`Adabas` 代表适应性数据库系统。它是由软件公司开发的，运行在 `IBM` 大型机上。它于 1971 年推出。这是一个面向大型机和 `Linux/Unix/Windows` 环境的 `OLTP-DBMS`。`Adabas` 是一种企业数据库管理系统（`DBMS`），旨在实现可靠性、高性能、可扩展性和低总拥有成本。

## 2. 阿里巴巴云 ApsaraDB for PolarDB
`PolarDB` 是一个云原生关系数据库，兼容 `MySQL`、`PostgreSQL` 和 `Oracle`。`ApsaraDB` 架构在单个集群中支持 5000 台物理机。它是为需要快速性能、高并发性和自动扩展的关键业务数据库应用程序而设计的。

## Adabas 与阿里巴巴云 ApsaraDB for PolarDB 的区别

| 编号 | Adabas | 阿里巴巴云 ApsaraDB for PolarDB |
| :--- | :--- | :--- |
| 1. | 它是由软件公司在 1971 年开发的。 | 它是阿里巴巴在 2013 年 8 月开发的。 |
| 2. | 它是一个面向大型机和 `Linux/Unix/Windows` 环境的 `OLTP-DBMS`。 | 它是一个云原生关系数据库，与 `MySQL`、`PostgreSQL` 和 `Oracle` 兼容。 |
| 3. | 它不支持内存功能。 | 它支持内存功能。 |
| 4. | `Adabas` 的服务器操作系统有 `BS2000`、`Linux`、`Unix`、`Windows`、`z/OS` 和 `z/VSE`。 | 在阿里巴巴云平台数据库中，有托管服务器操作系统。 |
| 5. | 它不支持 `XML` 格式。 | 它支持 `XML` 格式。 |
| 6. | 服务器端脚本是用自然语言完成的。 | 它还支持服务器端脚本。 |
| 7. | 它支持分区方法。 | 支持的分区方法是分片。 |
| 8. | 它支持带有附加产品 `Adabas SQL Gateway` 的 `SQL` 查询语言。 | 它还支持 `SQL` 查询语言。 |
| 9. | 它支持带有附加产品事件复制器的复制。 | 它还支持复制方法。 |
| 10. | `Adabas` 没有提供参照完整性的概念。因此，没有外键。 | `PolarDB` 的 `ApsaraDB` 提供了参照完整性的概念。因此，有外键。 |
| 11. | `Adabas` 的许可证是商业的。 | 阿里巴巴云 `ApsaraDB` for `PolarDB` 的许可也是商业的。 |
| 12. | `Adabas` 的主要数据库模型是多值数据库管理系统。 | 主要的数据库模型是关系型数据库管理系统。 |