# Hive和Oracle的区别

> 原文：[https://www.geeksforgeeks.org/difference-between-hive-and-oracle/](https://www.geeksforgeeks.org/difference-between-hive-and-oracle/)

## 1. `Hive`
`Hive`是一款开源的数据仓库软件。它建立在`Hadoop`之上。它还提供了类似于`SQL`的`HiveQL`。`Hive`用于查询和管理基于`Hadoop`构建的分布式数据集。`Hive`使用`RDBMS`作为主数据库模型。

## 2. Oracle
Oracle是由甲骨文公司开发的商业软件。Oracle广泛使用关系数据库管理系统。它用于运行在线事务处理和数据仓库。Oracle运行在最主要的操作系统上，如苹果操作系统、UNIX、视窗和Linux。Oracle有一个网络堆栈，允许来自不同平台的应用程序轻松地与Oracle通信。

## Hive与Oracle的区别

| 编号 | Hive | Oracle |
| :--- | :--- | :--- |
| 1. | 它是由Apache软件基金会开发的。 | 它由甲骨文公司开发。 |
| 2. | 它于2012年推出。 | 它于1980年推出。 |
| 3. | 用`Java`实现。 | 在`C`和`C++`中实现。 |
| 4. | 它使用分片分区方法在不同的节点上存储不同的数据。 | 它使用水平分区方法在不同的节点上存储不同的数据。 |
| 5. | 没有交易概念。 | 使用交易的`ACID`属性。 |
| 6. | 没有引用完整性的概念，也没有外键。 | 参照完整性在甲骨文中使用。 |
| 7. | 它是一个开源软件。 | 它是一个商业软件。 |
| 8. | 最终一致性方法确保分布式系统中的一致性。 | 即时一致性方法确保一致性。 |
| 9. | 它为用户定义的映射/缩减方法提供了应用编程接口。 | 它没有为用户定义的映射/缩减方法提供任何应用编程接口。 |
| 10. | `JDBC`、`ODBC`、`Thrift`是`Hive`中使用的API和访问方法。 | `JDBC`、`ODBC`、`ODP.NET`、`OCI`是Oracle中使用的API和访问方法。 |