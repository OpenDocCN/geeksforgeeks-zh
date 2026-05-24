# 甲骨文与 PouchDB 的区别

> 原文：[https://www.geeksforgeeks.org/difference-between-oracle-and-pouchdb/](https://www.geeksforgeeks.org/difference-between-oracle-and-pouchdb/)

## 甲骨文

`甲骨文`是一个关系型管理系统。它是由`甲骨文`公司在 1980 年开发的。它是第一个为网格计算设计的数据库，为管理信息和应用程序提供了最灵活、最经济的方式。它运行的主要平台有[视窗](https://www.geeksforgeeks.org/interesting-facts-about-windows/)、`UNIX`、`LINUX` 和 `MACOS`。它将关系数据库中用户通过应用程序或查询语言访问的数据称为 [`SQL`](https://www.geeksforgeeks.org/sql-tutorial/)。

## PouchDB

[`PouchDB`](https://www.geeksforgeeks.org/pouchdb/) 是一个开源的、[`NoSQL`](https://www.geeksforgeeks.org/introduction-to-nosql/) 的、在线的数据库。它是根据 `CouchDB` 设计的，这是一个为国家预防机制提供动力的 `NoSQL` 数据库。是用 [`JavaScript` 语言](https://www.geeksforgeeks.org/javascript-tutorial/)写的。不需要通过网络执行查询，因为 `PouchDB` 位于浏览器内部，因此速度非常快。它使用浏览器中的 `IndexedDB` 和 `WebSQL` 在本地存储数据。

## 甲骨文与 PouchDB 的区别

| 编号 | 甲骨文 | PouchDB |
| :--- | :--- | :--- |
| 1. | 它是由`甲骨文`公司在 1980 年开发的。 | 它由 `Apache` 软件基金会于 2012 年开发。 |
| 2. | 它是用 `C` 和 `C++`编写的。 | 它是用 `Javascript` 语言编写的。 |
| 3. | 它是一个商业软件。 | 它是一个开源软件。 |
| 4. | `甲骨文`的主要数据库模型是关系数据库管理系统。 | `PouchDB` 的主要数据库模型是文档存储。 |
| 5. | `甲骨文`的服务器操作系统有 `Solaris`、`Linux`、`OS X`、`Windows`。 | `PouchDB` 的服务器操作系统是无服务器的，需要一个 `JavaScript` 环境（浏览器，`Node.js`）。 |
| 6. | 它使用水平分区方法在不同的节点上存储不同的数据。 | 它使用分片分区方法在不同的节点上存储不同的数据。 |
| 7. | 即时一致性方法确保一致性。 | 最终一致性方法确保分布式系统中的一致性。 |
| 8. | 使用事务的 `ACID` 属性。 | 它不提供 `ACID` 事务。 |
| 9. | `Oracle` 支持的复制方法是主从复制，即主-主复制。 | `PouchDB` 支持的复制方法是主从复制，即主-主复制。 |
| 10. | 它根据 `SQL` 标准提供细粒度的访问权限。 | 它为用户提供了可按数据库定义的访问权限。 |