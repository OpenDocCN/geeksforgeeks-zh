# Derby 和 CouchDB 的区别

> 原文: [https://www.geeksforgeeks.org/difference-between-derby-and-couchdb/](https://www.geeksforgeeks.org/difference-between-derby-and-couchdb/)

## 1. Derby
`Derby` 是一个用 `Java` 实现的全功能、开源的关系数据库管理系统 (`RDBMS`)。顾名思义，它是由 `Apache Software Foundations` 开发的。它基于 `Java`、`JDBC` 和 `SQL` 标准。`Derby` 易于安装、部署和使用。它要么嵌入到 `Java` 应用程序中，要么用作数据库服务器。

## 2. CouchDB
`CouchDB` 是一个开源的面向文档的 `NoSQL` 数据库，使用多种格式和协议来存储、传输和处理其数据。它使用 `JSON` 来存储数据，使用 `MapReduce` 将 `JavaScript` 作为其查询语言，使用 `HTTP` 作为一个 `API`。它由 `Apache` 软件基金会开发，最初于 2005 年发布。是 `Erlang` 写的。

## Derby 和 CouchDB 的区别

| 序号 | Derby | CouchDB |
| :--- | :--- | :--- |
| 1 | 它是由 `Apache` 软件基金会在 1997 年开发的。 | 它是由 `Apache` 软件基金会在 2005 年开发的。 |
| 2 | 它是用 `Java` 语言编写的。 | 是用 `Erlang` 语言写的。 |
| 3 | `Derby` 的主要数据库模型是关系数据库管理系统。 | `CouchDB` 的主要数据库模型是文档存储。 |
| 4 | `Derby` 的服务器操作系统有 `Windows`、`macOs`、`Linux`、`Unix`、`BSD` 和 `z/OS`。 | `CouchDB` 服务器操作系统有 `Android`、`BSD`、`Linux`、`OS X`、`Solaris` 和 `Windows`。 |
| 5 | `Derby` 使用的 `API` 和其他访问方法是 `JDBC`。 | `CouchDB` 使用的 `API` 和其他访问方法是 `RESTful HTTP/JSON API`。 |
| 6 | 它只支持 `Java` 编程语言。 | 它支持 `C`、`C#`、`ColdFusion`、`Erlang`、`Java`、`JavaScript`、`PHP`、`PL/SQL`、`Python`、`Ruby` 等。 |
| 7 | 它支持主从复制方法。 | 它支持主从复制，主从复制。 |
| 8 | 在 `Derby` 中，分区是无法完成的。 | 在 `CouchDB` 中，分区可以通过分片来完成。 |
| 9 | 它是一个开源软件框架。 | 它是一个开源软件框架。 |
| 10 | 它支持根据 `SQL` 标准的细粒度访问权限。 | 它还支持用户访问权限。 |