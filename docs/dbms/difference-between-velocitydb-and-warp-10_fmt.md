# VelocityDB 和 Warp 10 之间的差异

> 原文: [https://www.geeksforgeeks.org/difference-between-velocitydb-and-warp-10/](https://www.geeksforgeeks.org/difference-between-velocitydb-and-warp-10/)

## 1. VelocityDB
是一个`.NET`对象数据库，可以嵌入/分布和扩展到图形数据模型（`VelocityGraph`）数据库是快速和低内存消耗。它是一个性能极高、易于使用、可扩展、可嵌入和可分发的对象数据库系统。

## 2. Warp 10
它是一个时间序列数据库管理系统，专门处理基于`LevelDB`或`HBase`的带时间戳的地理数据。Warp 10 的服务器操作系统是`Linux`、`OS X`、`Windows`。它是最先进的时间序列平台。它是一个开源的地理时间序列平台，旨在监控系统和物联网，并处理来自传感器的数据。

## VelocityDB 和 Warp 10 的区别

| 编号 | VelocityDB | Warp 10 |
| :--- | :--- | :--- |
| 1 | 它由`VelocityDB Inc.`开发，最初于 2011 年发布，目前`VelocityDB`的版本是 7.x | 它由`SenX`开发，最初于 2015 年发布。 |
| 3 | `VelocityDB`的服务器操作系统是任何支持`.NET` | 它有`Linux`、`OS X`、`Windows`服务器操作系统。 |
| 4 | 它的主要数据库模型是图形数据库和面向对象数据库。 | 它的主要数据库模型是时间序列数据库管理系统。 |
| 6 | `VelocityDB`支持`.Net`编程语言。 | `Warp 10`中没有这种支持的编程语言。 |
| 7 | `VelocityDB`的`API`和其他访问方法是`.NET` | `Warp 10`支持`HTTP API`、`Jupyter`、`WebSocket`。 |
| 8 | 它有一个数据模式。 | `Warp 10`的数据模式是无模式的 |
| 9 | 它有实现语言——`c#`。 | `Warp 10`的实现语言是`Java`。 |
| 10 | 它的事务概念是`ACID`（原子性、一致性、隔离性和持久性）。 | `Warp 10`中缺少交易概念。 |
| 11 | 缺少复制方法。 | 有复制方法-可选择的复制因子。 |
| 12 | 它有直接的一致性概念。 | 它有最终的一致性概念。 |
| 13 | 它的划分方法是分片。 | 它的划分方法也是分片。 |