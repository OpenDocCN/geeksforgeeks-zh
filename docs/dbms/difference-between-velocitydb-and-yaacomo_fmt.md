# VelocityDB 和 Yaacomo 的区别

> 原文: [https://www.geeksforgeeks.org/difference-between-velocitydb-and-yaacomo/](https://www.geeksforgeeks.org/difference-between-velocitydb-and-yaacomo/)

**1. VelocityDB:**
是一个`.NET`对象数据库，可以嵌入/分布和扩展到图形数据模型(`VelocityGraph`)。数据库是快速和低内存消耗。它是一个性能极高、易于使用、可扩展、可嵌入和可分发的对象数据库系统。

**2. Yaacomo:**
这是一个基于`OpenCL`的内存数据库管理系统，用于实时分析和大数据解决方案，是作为即插即用解决方案开发的。它旨在通过并行计算有效利用硬件。

**VelocityDB 和 Yaacomo 的区别:**

| No | VelocityDB | Yaacomo |
| --- | --- | --- |
| 1 | 它由`VelocityDB Inc.`开发，最初于 2011 年发布，目前`VelocityDB`的版本是 7.x | 它由`Q2WEB GmbH`开发，最初于 2009 年发布。 |
| 2 | 其服务器操作系统`VelocityDB`是任何支持`.NET` | 其服务器操作系统`Yaacomo`是`Android`、`Linux`、`Windows`。 |
| 3 | 它的主要数据库模型是`图形数据库`和`面向对象数据库` | 它的主要数据库模型是`关系数据库管理系统`。 |
| 4 | 它支持`.Net`编程语言。 | 它不支持任何编程语言 |
| 5 | `VelocityDB`的`API`和其他访问方法是`.NET` | `Yaacomo`的`API`和其他访问方法是`JDBC`，`ODBC`。 |
| 6 | 实现语言是`C#`。 | 它没有任何实现语言。 |
| 7 | 缺少复制方法 | `Yaacomo`的复制方法是`主从复制`。 |
| 8 | `VelocityDB`中存在分片分区方法。 | `Yaacomo`的`水平分割`法。 |
| 9 | 它没有`外键` | 它持有`外键`。 |