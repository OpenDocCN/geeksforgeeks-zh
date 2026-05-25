# Valentina 服务器与 Virtuoso 的区别

> 原文：[https://www.geeksforgeeks.org/difference-between-valentina-server-and-virtuoso/](https://www.geeksforgeeks.org/difference-between-valentina-server-and-virtuoso/)

**1. Virtuoso：**
它是一个中间件，支持对表示为关系表和/或属性图的数据进行管理。它是一个多模型混合关系数据库管理系统，主要的数据库模型有图形数据库管理系统、原生 XML 数据库管理系统、关系数据库管理系统、RDF 存储、搜索引擎。它是为利用操作系统线程支持和多个 CPU 而设计的。对象关系数据库支持实体完整性和引用完整性。

**2. 瓦伦蒂娜服务器：**
它是一个对象关系数据库和报表服务器以及快速对象关系数据库服务器。它包括集成数据库服务器，瓦伦蒂娜数据库服务器和 SQLite 数据库服务器。它是一个功能齐全、符合标准的基于 SQLite 的多用户访问数据库服务器。

## Valentina Server 与 Virtuoso 的区别

| 序号 | 瓦伦蒂娜服务器 | Virtuoso |
| :--- | :--- | :--- |
| 1 | 由 Paradigma 软件开发，最初于 1994 年发布，当前版本的 Valentina Server 是 `5.7.5`。 | 由 Virtuoso 开发，最初于 1998 年发布，目前于 2019 年 5 月发布。 |
| 2 | 瓦伦蒂娜服务器的服务器操作系统是 Linux、OS X、Windows。 | 服务器操作系统 - AIX，FreeBSD，惠普-UX，Linux，OS X，Solaris，Windows。 |
| 3 | 它的主要数据库模型是关系数据库管理系统。 | 它的主要数据库模型是图形数据库、原生 XML 数据库、关系数据库、RDF 存储、搜索引擎，其辅助数据库模型是文档存储。 |
| 4 | 瓦伦蒂娜服务器支持 `.Net`、`C`、`C#`、`C++`、Objective-C、`PHP`、Ruby、Visual Basic、Visual Basic.NET 编程语言。 | Virtuoso 支持 `.Net`、`C`、`C#`、`C++`、`Java`、`JavaScript`、`Perl`、`PHP`、`Python`、`Ruby`、Visual Basic 编程语言。 |
| 5 | Valentina Server 的 API 等访问方式是 `ODBC`。 | Virtuoso 支持 ADO.NET、GeoSPARQL、HTTP API、JDBC、Jena、RDF API、`ODBC`、OLE DB、RDF4J API、RESTful HTTP API、芝麻街 REST HTTP 协议、SOAP、webservices、WebDAV、XPath、XQuery、XSLT。 |
| 6 | 是的，瓦伦蒂娜服务器有一个数据模式。 | 是的，Virtuoso 有一个数据模式。 |
| 7 | 它没有实现语言——`C#`。 | Virtuoso 的实现语言是 `C`。 |
| 8 | 瓦伦蒂娜服务器中缺少事务概念。 | 它的事务概念是 `ACID`（原子性、一致性、隔离性和持久性）。 |
| 9 | 瓦伦蒂娜服务器没有一致性概念。 | 是的，Virtuoso 有一致性的概念。 |
| 10 | 是的，它有外键。 | 它持有外键。 |
| 11 | Valentina 服务器中缺少复制方法。 | Virtuoso 的复制方法基于链式、星型和双向复制，主-主复制，主从复制。 |
| 12 | Valentina 服务器中缺少分区方法。 | 它不支持分片分区方法。 |