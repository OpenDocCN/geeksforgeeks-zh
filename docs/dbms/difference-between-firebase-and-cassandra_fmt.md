# Firebase与Cassandra的区别

> 原文：[https://www.geeksforgeeks.org/difference-between-firebase-and-cassandra/](https://www.geeksforgeeks.org/difference-between-firebase-and-cassandra/)

## 1. Firebase
`Firebase`是谷歌在2012年开发的。它是一个实时存储和同步数据的数据库。它是云托管的实时文档存储，并提供从任何设备（网络、移动）访问数据的灵活性。`iOS`、`Android`和`JavaScript`客户端共享一个实时数据库实例，并自动接收最新数据的更新。

## 2. Cassandra
`Cassandra`是一个免费开源的、分布式的、宽栏目的`NoSQL`数据库管理系统。它由`Apache`软件基金会开发，最初于2008年7月发布。`Cassandra`旨在处理许多商用服务器上的大量数据，提供高可用性，没有单点故障。

## Firebase与Cassandra的区别

| 序号 | Firebase | Cassandra |
| :--- | :--- | :--- |
| 1. | 它是谷歌在2012年开发的。 | 它是由`Apache`软件基金会在2008年开发的。 |
| 2. | `Firebase`的主要数据库模型是文档存储。 | `Cassandra`的主要数据库模型是宽列存储。 |
| 3. | 它不支持复制方法。 | 它支持可选择复制因子作为复制方法。 |
| 4. | `Firebase`的服务器操作系统是托管的。 | `Cassandra`服务器操作系统是`BSD`、`Linux`、`OS X`、`Windows`。 |
| 5. | 它是一个商业软件。 | 它是一个开源软件框架。 |
| 6. | 采用`Android`、`iOS`、`JavaScript` `API`、`RESTful HTTP API`作为`API`等访问方式。 | `Cassandra`使用的`API`和其他访问方法是专有协议“节俭”。 |
| 7. | 它不支持分区方法。 | 它支持带有分片的分区方法。 |
| 8. | 最终和即时一致性方法确保分布式系统中的一致性。 | 最终和即时一致性方法确保分布式系统中的一致性。 |
| 9. | 它更适合小规模应用。 | 更适合大规模应用。 |
| 10. | 它不太安全。 | 它比`Firebase`提供了更多的安全性。 |