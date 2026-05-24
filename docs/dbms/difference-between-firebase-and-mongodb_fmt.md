# Firebase 和 MongoDB 的区别

> 原文: [https://www.geeksforgeeks.org/difference-between-firebase-and-mongodb/](https://www.geeksforgeeks.org/difference-between-firebase-and-mongodb/)

## 1. Firebase
`Firebase` 是谷歌在 2012 年开发的。它是一个实时存储和同步数据的数据库。这是一个云托管的实时文档存储，并提供了从任何设备访问数据的灵活性。`JavaScript` 客户端共享一个实时数据库实例，并自动接收最新数据的更新。

## 2. MongoDB
`MongoDB` 是一个跨平台的面向文档的非关系（`NoSQL`）数据库程序，不需要数据的行列格式。它提供了高性能，并且本质上是动态的，不需要像传统的关系数据库管理系统那样预定义模式。它是一个开源文档数据库，以键值对的形式存储数据。`MongoDB` 由 `MongoDB Inc.` 开发，最初于 2009 年 2 月 11 日发布。用 `C++`、`Go`、`JavaScript`、`Python` 语言编写。`MongoDB` 提供了高速度、高可用性和高扩展性。

## Firebase 和 MongoDB 的区别

| 序号 | FIREBASE | MONGODB |
| :--- | :--- | :--- |
| 1. | 它是谷歌在 2012 年开发的。 | 它是由 `MongoDB Inc.` 在 2009 年开发的。 |
| 2. | 它支持 `Objective C`、`Java` 和 `JavaScript` 作为编程语言。 | 它支持 `C`、`C#`、`Java`、`JavaScript`、`PHP`、`Lua`、`Python`、`R`、`Ruby` 作为编程语言。 |
| 3. | 这是一个商业数据库。 | 这是一个开源数据库。 |
| 4. | `Firebase` 的服务器操作系统是托管的。 | `MongoDB` 的服务器操作系统有 `Solaris`、`Linux`、`OS X`、`Windows`。 |
| 5. | 它不支持任何复制方法。 | `MongoDB` 支持的复制方法是主从复制。 |
| 6. | 它不支持地图缩减方法。 | 它支持地图缩减方法。 |
| 7. | 它不支持任何分区方法。 | 它支持分片分区方法。 |
| 8. | `Android`、`iOS`、`JavaScript API`、`RESTful HTTP API` 作为 API 等访问方式。 | 使用 `JSON` 的专有协议被用作 API 和其他访问方法。 |
| 9. | 它更适合小规模应用。 | 更适合大规模应用。 |
| 10. | 它不太安全。 | 它比 `Firebase` 提供了更多的安全性。 |