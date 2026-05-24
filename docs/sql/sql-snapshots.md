# SQL 快照

> 原文:[https://www.geeksforgeeks.org/sql-snapshots/](https://www.geeksforgeeks.org/sql-snapshots/)

**快照**是数据库中该表的最近副本，或者是表的行/列的子集。创建并随后维护快照的 SQL 语句通常从驻留在服务器上的数据库中读取数据。使用创建快照 SQL 命令在目标系统上创建快照。远程表立即从主表中定义和填充。

这些用于在分布式数据库之间动态复制数据。有两种类型的快照可用。

1.  简单快照
2.  复杂快照

**简单快照:**
在**简单快照**中，每行基于单个远程表中的单个行。这包括单个表或单个表中的简单行选择。

**示例–**

```sql
CREATE SNAPSHOT emp_snap 
as select * from emp;

```

**复杂快照:**
在**复杂快照**中，一行可以通过 GROUP BY 操作或多表连接的结果基于远程表中的多行。这包括连接的表、视图或分组的复杂 SELECT 语句查询。

**示例–**

```sql
CREATE SNAPSHOT sampleSnps1 
AS SELECT student.rollno, student.name 
FROM student
UNION ALL
SELECT new_student.rollno, new_student.name 
FROM new_student;

```

**优势:**

*   当存在表的本地只读副本时，响应时间会缩短。
*   一旦在远程数据库上构建快照，如果包含从中构建快照的数据的节点不可用。无需访问不可用的数据库即可使用快照。
*   减轻网络负荷。
*   数据子集化。
*   断开连接的计算。
*   大规模部署。

**缺点:**

*   当主数据库脱机时，快照不可访问。
*   它不支持全文索引。
*   如果数据频繁快速更改，快照将耗尽磁盘空间。
*   随着快照数量的增加，磁盘空间会出现问题。

**应用:**

*   保护数据。
*   维护数据历史记录。
*   用于测试应用软件。
*   用于数据挖掘。
*   当信息因人为错误或数据损坏而丢失时，恢复数据。