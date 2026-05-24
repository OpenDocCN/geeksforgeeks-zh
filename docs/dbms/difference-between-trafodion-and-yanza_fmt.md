# Trafodion 和 Yanza 的区别

> 原文: [https://www.geeksforgeeks.org/difference-between-trafodion-and-yanza/](https://www.geeksforgeeks.org/difference-between-trafodion-and-yanza/)

## 1. Trafodion
这是事务性的 `Hadoop` 数据库管理系统。这是一个基于 `Hadoop` 的网络级 `SQL` 解决方案，支持 `Apache Hadoop` 上的事务性或操作性工作负载。“Trafodion”这个名字发音为“Tra-vod-eee-on”。它是一个运行在 `Apache Hadoop` 上的关系数据库管理系统，使用并行感知查询优化器为大数据环境中的事务性或操作性工作负载以及大型数据集提供支持。

## 2. Yanza
是 `Yanza` 为[物联网](https://www.geeksforgeeks.org/introduction-to-internet-of-things-iot-set-1/)应用开发的时间序列数据库管理系统。它的服务器操作系统是 `Window`，支持 `HTTP API`。

## Trafodion 和 Yanza 的区别

| 编号 | Trafodion | Yanza |
| :--- | :--- | :--- |
| 1 | 它由最初由惠普开发的 `Apache` 软件基金会开发。最初于 2014 年发布。 | 它由 `Yanza` 开发，最初于 2015 年发布。 |
| 2 | `Linux` 是 `Trafodion` 的服务器操作系统。 | `Windows` 是 `Yanza` 的服务器操作系统。 |
| 3 | 它的主要数据库模型是关系数据库管理系统。 | 它的主要数据库模型是时间序列数据库管理系统。 |
| 4 | 支持 `JDBC`/`ODBC`/`ADO.NET` 的所有语言。 | 它支持任何支持 `HTTP` 调用的语言。 |
| 5 | `ADO.NET`、`JDBC`、`ODBC` 是 `Trafodion` 的 `API` 和其他访问方法。 | `YCQL`，一个基于 `SQL` 的灵活模式应用程序接口，其根源在于卡珊德拉查询语言、应用程序接口和其他访问方法。 |
| 6 | 它有数据模式。 | `Yanza` 的数据模式是无模式的。 |
| 7 | 其实现语言有 `Java` 和 `C++`。 | 它没有任何实现语言。 |
| 8 | 它有 `ACID` 事务概念。 | 它没有事务概念。 |
| 9 | 通过 `HBase` 是 `Trafodion` 的复制方法。 | `Yanza` 缺少复制方法。 |
| 10 | 它包含即时一致性概念。 | 它有立即一致性的概念。 |
| 11 | 它有外键的概念。 | 它没有外键的概念。 |