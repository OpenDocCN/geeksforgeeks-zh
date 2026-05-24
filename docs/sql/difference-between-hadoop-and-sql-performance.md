# Hadoop 和 SQL 性能的差异

> 原文:[https://www . geeksforgeeks . org/Hadoop 和 sql 之间的差异-性能/](https://www.geeksforgeeks.org/difference-between-hadoop-and-sql-performance/)

**Hadoop:** [Hadoop](https://www.geeksforgeeks.org/hadoop-an-introduction/) 是一个用 Java 编写的开源软件框架，用于存储数据和处理大小从千兆字节到千兆字节的大型数据集。Hadoop 是一个分布式文件系统，可以跨计算机存储和处理海量数据集群。由于 Hadoop 是基于 Java 的，因此它与所有平台都兼容。Hadoop 有两个核心层，即处理/计算层(MapReduce)和存储层(Hadoop 分布式文件系统)。Hadoop 跨计算机集群运行代码，并对跨商品服务器集群的巨大数据集执行离线批处理。然而，Hadoop 不是 SQL 的替代品，它们的使用取决于个人需求。与性能相比，Hadoop 在处理结构化、半结构化和非结构化数据方面的速度和能力都有所提高，因此比 SQL 更胜一筹。

**SQL 性能:** [结构化查询语言(SQL)](https://www.geeksforgeeks.org/structured-query-language/) 是一种在数据库中操作、检索和存储数据的标准语言。关系数据库使用 SQL 作为维护和操作数据的标准。诸如“选择”、“插入”、“更新”、“删除”、“创建”和“删除”等 SQL 命令可用于存储、更新或检索数据库中的数据。使用 SQL 的一些常见关系数据库管理系统有 Oracle、微软 SQL Server、Sybase、Access、Ingres 等。然而，随着数据量(或大数据)的增加，使用关系数据库存储如此大量的数据变得越来越困难。适用于结构化模式，但对于大数据，它没有固定模式，而是半结构化数据。大数据的 3 V:数量、种类和速度是导致 NoSQL 数据库出现的主要原因。从名称上看，很明显 SQL 不能再为 NoSQL 数据库的数据操作服务了。在这方面，Hadoop 比 SQL 有优势。

下表列出了 Hadoop 和 SQL 性能之间的差异:

 用于并行处理的网络

| 特征 | Hadoop | SQL 性能 |
| --- | --- | --- |
| **结构** | 无固定模式 | 固定模式 |
| **数据格式** | 结构化、 半结构化或非结构化数据 | 结构化数据 |
| **数据量** | Hadoop 在低数据量和高数据量上的表现都异常出色 | SQL 在低数据量上的表现更好 |
| **数据处理** | Hadoop 支持大规模离线批量处理被称为 OLAP | SQL 支持实时 较慢的 |
| **吞吐量** | 较高的吞吐量 | 较低的吞吐量 |
| **延迟** | Hadoop 无法非常快速地从数据集中提取特定记录因此具有低延迟 | SQL 可以非常快速地从数据集中提取特定记录因此具有高延迟 |
| 垂直可扩展性这意味着在现有机器上增加更多的硬件或 CPU |
| **数据存储** | 数据可以以表格、键值对等形式存储 | 数据只能以表格形式存储。 |
| **完整性** | 低完整性 | 高完整性 |
| **数据多样性** | Hadoop 处理大数据并支持多种数据 | SQL 不支持多种数据 |
| **更新【t19 因此，数据更新实际上是不可能的** | SQL 是写一次，读和更新多次。因此数据更新非常容易完成 |
| **ACID Properties** | 它并不完全符合 ACID properties | 它完全符合 ACID Properties |
| **License** | Hadoop 是自由开源软件 | SQL 是许可的 |