# 【MySQL 和 PostgreSQL 的区别

> 原文:[https://www . geesforgeks . org/区别-MySQL-和-postgresql/](https://www.geeksforgeeks.org/difference-between-mysql-and-postgresql/)

数据库是以易于管理和更新的方式构建的信息集合。为了使这项任务变得更容易，已经创建了各种[数据库管理系统(DBMS)](https://www.geeksforgeeks.org/dbms/) 。这些包括 MySQL、PostgreSQL、MongoDB、Redis 等。

**1。** [**MySQL**](https://www.geeksforgeeks.org/mysql-common-mysql-queries/)
它是最著名的、开源的**关系数据库管理系统(RDMS)** 。该表中的数据存储在表中，这使得执行 CRUD 操作(创建、读取、更新和删除)变得容易。MySQL 的一些特性包括:

*   快速、简单、可靠。
*   可用于大型和小型应用。
*   提供高扩展性

**2。PostgreSQL:**
它是一个强大的开源**对象关系数据库系统**。由于其高稳定性，它以低维护工作量提供了良好的性能。PostgreSQL 是第一个实现**多版本并发控制(MVCC)** 特性的 DBMS。PostgreSQL 的一些亮点是:

*   支持大量语言。
*   它提供高级安全功能。
*   它有**地理标记**支持。

**MySQL 与 PostgreSQL 的区别:**

<figure class="table">

| s。没有。 | 关系型数据库 | 一种数据库系统 |
| --- | --- | --- |
| 1。 | It is the most popular database. | It is the most **advanced** database. |
| --- | --- | --- |
| 2。 | It is a database management system based on **relation.** | It is a relational DBMS based on **object.** |
| 3。 | ACID complaints are only when used with InnoDB and NDB cluster engines. | ACID complained from the bottom up. |
| 4。 | The implementation language is **C/C++**. | The implementation language is **c** . |
| 5。 | CASCADE option is not supported. support | 串联选项。 |
| 6。 | 图像使用者界面工具提供的是 **MySQL 工作台** | **PgAdmin** provides |
| 7。 | Local, bitmap and expression indexes are not supported. | It supports all this. |
| 8。 | Materialized views and table inheritance are not supported. | PostgreSQL provides both. |
| 9。 | SQL only supports **standard data type** . | Support **advanced data types** , such as array, hstore and user-defined types. |
| 10。 | Provide SQL **limited MVCC support** (in InnoDB) | **Full MVCC** support. |

</figure>