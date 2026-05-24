# 4D 与阿里云 ApsaraDB for PolarDB 的区别

> 原文：[https://www.geeksforgeeks.org/difference-between-4d-and-alibaba-cloud-apsaradb-for-polardb/](https://www.geeksforgeeks.org/difference-between-4d-and-alibaba-cloud-apsaradb-for-polardb/)

**1. 第四维 (4D)：**
第四维是一个[关系数据库管理系统](https://www.geeksforgeeks.org/difference-between-rdbms-and-dbms/)和由 Laurent Ribardière 开发的 `IDE`。`4D` 可以作为服务器运行，这样多个客户端可以管理一个数据库。`4D` 创建于 1984 年，麦金塔电脑在 1987 年的公开发行稍有延迟。这是一个具有集成数据库管理系统的应用程序开发环境。

**2. 阿里云 ApsaraDB for PolarDB：**
`PolarDB` 是一个云原生关系数据库，兼容 [MySQL](https://www.geeksforgeeks.org/sql-tutorial/#mysql)、[PostgreSQL](https://www.geeksforgeeks.org/what-is-postgresql-introduction/) 和 Oracle。`ApsaraDB` 架构在单个集群中支持 5000 台物理机。它是为需要快速性能、高并发性和自动扩展的关键业务数据库应用程序而设计的。

**4D 与阿里云 ApsaraDB for PolarDB 的区别：**

| 编号 | 4D | 阿里云 ApsaraDB for PolarDB |
| :--- | :--- | :--- |
| 1. | 由 `4D` 公司于 1984 年开发。 | 由阿里巴巴于 2013 年 8 月开发。 |
| 2. | 这是一个具有集成数据库管理系统的应用程序开发环境。 | 它是一个云原生关系数据库，与 `MySQL`、`PostgreSQL` 和 `Oracle` 兼容。 |
| 3. | `4D` 的服务器操作系统是 `OS X` 和 `Windows`。 | 在阿里云 `ApsaraDB` for `PolarDB` 中，托管服务器操作系统。 |
| 4. | 它不能作为云服务使用。 | 它可以作为云服务使用。 |
| 5. | 它不支持内存功能。 | 它支持内存功能。 |
| 6. | 支持的编程语言是 `PHP`。 | 支持的编程语言有 `Java` 和 `Python`。 |
| 7. | 没有分区方法。 | 只有一种分区方法——分片。 |
| 8. | 支持的应用编程接口和其他访问方法有 `ODBC`、`RESTful HTTP API` 和 `SOAP` 网络服务。 | 支持的 `API` 和其他访问方法有 `JDBC` 和 `ODBC`。 |
| 9. | 它只支持一种复制方法——主-主复制。 | 它还支持复制方法。 |