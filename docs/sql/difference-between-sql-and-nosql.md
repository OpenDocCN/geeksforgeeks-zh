# SQL 和 NoSQL 的区别

> 原文:[https://www . geesforgeks . org/SQL 和 nosql 之间的区别/](https://www.geeksforgeeks.org/difference-between-sql-and-nosql/)

先决条件–[SQL](https://www.geeksforgeeks.org/sql-tutorial/)、 [NoSQL](https://www.geeksforgeeks.org/introduction-to-nosql/)
在选择数据库时，最大的决策是选择**关系型(SQL)** 或非关系型(NoSQL) 数据结构。虽然这两个数据库都是可行的选择，但用户在做出决定时必须记住两者之间的某些关键差异。

**主要区别:**

1.  **Type –** 
    SQL databases are primarily called as Relational Databases (RDBMS); whereas NoSQL database are primarily called as non-relational or distributed database. 
2.  **Language –** 
    SQL databases defines and manipulates data based structured query language (SQL). Seeing from a side this language is extremely powerful. SQL is one of the most versatile and widely-used options available which makes it a safe choice especially for great complex queries. But from other side it can be restrictive. SQL requires you to use predefined schemas to determine the structure of your data before you work with it. Also all of your data must follow the same structure. This can require significant up-front preparation which means that a change in the structure would be both difficult and disruptive to your whole system. 

    NoSQL 数据库具有非结构化数据的动态模式。数据以多种方式存储，这意味着它可以是面向文档的、面向列的、基于图形的，或者组织为键值存储。这种灵活性意味着无需先定义结构就可以创建文档。每个文档也可以有自己独特的结构。语法因数据库而异，您可以随时添加字段。

3.  **The Scalability –** 
    In almost all situations SQL databases are vertically scalable. This means that you can increase the load on a single server by increasing things like RAM, CPU or SSD. But on the other hand NoSQL databases are horizontally scalable. This means that you handle more traffic by sharding, or adding more servers in your NoSQL database. It is similar to adding more floors to the same building versus adding more buildings to the neighborhood. Thus NoSQL can ultimately become larger and more powerful, making these databases the preferred choice for large or ever-changing data sets. 
4.  **The Structure –** 
    SQL databases are table-based on the other hand NoSQL databases are either key-value pairs, document-based, graph databases or wide-column stores. This makes relational SQL databases a better option for applications that require multi-row transactions such as an accounting system or for legacy systems that were built for a relational structure. 
5.  **Property followed –** 
    SQL databases follow ACID properties (Atomicity, Consistency, Isolation and Durability) whereas the NoSQL database follows the Brewers CAP theorem (Consistency, Availability and Partition tolerance). 
6.  **Support –** 
    Great support is available for all SQL database from their vendors. Also a lot of independent consultations are there who can help you with SQL database for a very large scale deployments but for some NoSQL database you still have to rely on community support and only limited outside experts are available for setting up and deploying your large scale NoSQL deployments. 

    SQL 数据库的一些例子包括 PostgreSQL、MySQL、Oracle 和微软的 SQL Server。NoSQL 数据库的例子包括 Redis、RavenDB Cassandra、MongoDB、BigTable、HBase、Neo4j 和 CouchDB。

**SQL vs NoSQL 的重点亮点:**

<figure class="table">

| 结构化查询语言 | NoSQL |
| --- | --- |
| Relational database management system (RDBMS) | Non-relational or distributed database system. |
| These databases have fixed or static or predefined patterns. | They have dynamic modes. |
| These databases are not suitable for hierarchical data storage. | These databases are most suitable for hierarchical data storage. |
| These databases are most suitable for complex queries. | These databases are not suitable for complex queries. |
| Longitudinal scalability | Transverse scalability |
| Comply with ACID attribute | Compliance with CAP (consistency, availability, partition tolerance) |

</figure>