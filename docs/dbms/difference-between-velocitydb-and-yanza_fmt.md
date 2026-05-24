# VelocityDB 和 Yanza 的区别

> 原文: [https://www.geeksforgeeks.org/difference-between-velocitydb-and-yanza/](https://www.geeksforgeeks.org/difference-between-velocitydb-and-yanza/)

## 1. VelocityDB
是一个`.NET`对象数据库，可以嵌入/分布和扩展到图形数据模型(`VelocityGraph`)。数据库是快速和低内存消耗。`VelocityDB`是一个性能极高、易于使用、可扩展、可嵌入和可分发的对象数据库系统。

## 2. Yanza
这是由`Yanza`开发的面向物联网应用的时间序列数据库管理系统。它的服务器操作系统是`Window`，支持`HTTP API`。

## VelocityDB 和 Yanza 的区别

| No | VelocityDB | Yanza |
| :--- | :--- | :--- |
| 1 | 由`VelocityDB Inc.`开发，最初于 2011 年发布，目前`VelocityDB`的版本为`7.x` | 由`Yanza`开发，最初于 2015 年发布。 |
| 2 | `VelocityDB`的服务器操作系统是任何支持`.NET` | `Yanza`的服务器操作系统是`Windows`。 |
| 3 | 它的主要数据库模型是图形数据库和面向对象数据库 | 它的主要数据库模型是时间序列数据库管理系统。 |
| 4 | `VelocityDB`支持`.Net`编程语言。 | `Yanza`支持任何支持`HTTP`调用的语言。 |
| 5 | `VelocityDB`的`API`和其他访问方法是`.Net` | `Yanza`支持`HTTP API`。 |
| 6 | 是的，`VelocityDB`有一个数据模式。 | `Yanza`的数据方案是无模式的。 |
| 7 | 它有实现语言——`c#`。 | 它没有任何实现语言。 |
| 8 | 事务概念是`ACID`(原子性、一致性、隔离性和持久性)。 | 它不包含事务概念。 |
| 9 | 缺少复制方法 | `Yanza`缺少复制方法。 |
| 10 | `VelocityDB`具有即时一致性概念。 | `Yanza`有立即一致性的概念。 |
| 11 | 分片是`VelocityDB`的一种划分方法。 | 它没有分区方法。 |