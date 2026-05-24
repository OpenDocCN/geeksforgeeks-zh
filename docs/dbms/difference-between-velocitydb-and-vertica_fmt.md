# VelocityDB 和 Vertica 的区别

> 原文: [https://www.geeksforgeeks.org/difference-between-velocitydb-and-vertica/](https://www.geeksforgeeks.org/difference-between-velocitydb-and-vertica/)

## 1. Vertica
它是柱状关系型数据库管理系统，旨在处理现代分析工作负载并实现快速查询性能。其总部位于美国马萨诸塞州剑桥。它是一个独立于基础设施的平台，通过它，它支持在多个云平台（`AWS`、`Google Cloud`、`Azure`）上、内部以及天真地在 `Hadoop` 节点上的部署。其分析平台社区版是免费提供的，但有一定的限制。

## 2. VelocityDB
是的 `.NET` 对象数据库，可以嵌入/分布和扩展到图形数据模型（`VelocityGraph`）数据库，速度快，内存消耗低。`VelocityDB` 是一个性能极高、易于使用、可扩展、可嵌入和可分发的对象数据库系统。

## VelocityDB 和 Vertica 的区别

| 编号 | VelocityDB | Vertica |
| --- | --- | --- |
| 1 | 它由 `VelocityDB Inc.` 开发，最初于 2011 年发布。 | 它由 `Vertica` / `Micro Focus` 开发，最初于 2005 年发布。 |
| 2 | `VelocityDB` 的服务器操作系统是任何支持 `.NET` | `Vertica` 的服务器操作系统是 `Linux` |
| 3 | 它的主要数据库模型是图形数据库和面向对象数据库 | 它的主要数据库模型是关系数据库管理系统。 |
| 4 | `VelocityDB` 中缺少辅助数据库模型 | `Vertica` 的二级数据库模型是文档存储。 |
| 5 | 它支持 `.Net` 编程语言。 | 它支持 `C++`、`Java`、`Perl`、`Python`、`R`、编程语言。 |
| 6 | `VelocityDB` 的 `API` 和其他访问方法是 `.net` | `Vertica` 的 `API` 和其他访问方法是 `ADO.NET`、`JDBC`、`Kafka`、`ODBC`、专有协议、`RESTful HTTP API`。 |
| 7 | 实现语言是 `C#`。 | 它没有任何实现语言。 |
| 8 | 缺少复制方法 | `Vertica` 的复制方法是主-主复制。 |
| 9 | 它没有外键。 | 它持有外键。 |