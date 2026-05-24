# XAP 和 Virtuoso 的区别

> 原文：[https://www.geeksforgeeks.org/difference-between-xap-and-virtuoso/](https://www.geeksforgeeks.org/difference-between-xap-and-virtuoso/)

## 1. Virtuoso

Virtuoso 是一个中间件，支持对表示为关系表和/或属性图的数据进行管理。它是一个多模型混合关系数据库管理系统，主要数据库模型为图形数据库管理系统、原生 XML 数据库管理系统、关系数据库管理系统、RDF 存储、搜索引擎。它是为利用操作系统线程支持和多个 CPU 而设计的。对象关系数据库支持实体完整性和引用完整性。

## 2. XAP

XAP 高性能内存数据网格适用于任务关键型应用程序，并提供了一组基本的数据存储功能，如事务、索引和查询语言（类似于 SQL 的查询）。它是一种用于安装和分发应用软件的文件格式。

## 3. XAP 与 Virtuoso 的区别

| 编号 | XAP | Virtuoso |
| :--- | :--- | :--- |
| 1 | 由 Gigaspaces Technologies 开发，最初于 2000 年发布，目前于 2019 年 6 月发布。 | 由 Virtuoso 开发，最初于 1998 年发布，目前于 2019 年 5 月发布。 |
| 2 | 它的主要数据库模型是文档存储和键值存储。 | 它的主要数据库模型是图形数据库、原生 XML 数据库、关系数据库、RDF 存储、搜索引擎。 |
| 3 | 它的二级数据库模型是面向对象的数据库管理系统。 | 它的二级数据库模型是文档存储。 |
| 4 | XAP 的服务器操作系统：Linux、macOS、Solaris、Windows。 | Virtuoso 的服务器操作系统：AIX、FreeBSD、HP-UX、Linux、OS X、Solaris、Windows。 |
| 5 | XAP 支持 `GigaSpace LRMI`、`Hibernate`、`JCache`、`JDBC`、`JPA`、`ODBC`、`RESTful HTTP API`、`Spring Data`。 | Virtuoso 支持 `ADO.NET`、`GeoSPARQL`、`HTTP API`、`JDBC`、`Jena RDF API`、`ODBC`、`OLE DB`、`RDF4J API`、`RESTful HTTP API`、`Virtuoso REST HTTP Protocol`、`SOAP`、`Web Services`、`WebDAV`、`XPath`、`XQuery`、`XSLT`。 |
| 6 | XAP 有 `ACID`（原子性、一致性、隔离性和持久性）事务概念。 | 它的事务概念是 `ACID`（原子性、一致性、隔离性和持久性）。 |
| 7 | XAP 复制方法：主-主复制和主从复制。 | Virtuoso 的复制方法基于链式、星型和双向复制，主-主复制，主从复制。 |
| 8 | XAP 的分区方法是分片。 | 它不支持分片分区方法。 |
| 9 | XAP 支持 `.Net`、`C++`、`Java` 编程语言。 | Virtuoso 支持 `.Net`、`C`、`C#`、`C++`、`Java`、`JavaScript`、`Perl`、`PHP`、`Python`、`Ruby`、`Visual Basic` 编程语言。 |
| 10 | 它有立即一致性的概念。 | 是的，Virtuoso 有一致性的概念。 |
| 11 | XAP 的实现语言是 `Java`、`C++`、`.Net`。 | Virtuoso 的实现语言是 `C`。 |
| 12 | 它没有外键。 | 它持有外键。 |
| 13 | 它有类似 SQL 的查询语言和 DML 语句。 | 是的，Virtuoso 有 `SQL`。 |