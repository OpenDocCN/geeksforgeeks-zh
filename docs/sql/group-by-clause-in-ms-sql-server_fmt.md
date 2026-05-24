# MS SQL Server 中的分组依据子句

> 原文：[https://www.geeksforgeeks.org/group-by-clause-in-ms-sql-server/](https://www.geeksforgeeks.org/group-by-clause-in-ms-sql-server/)

本文将详细讨论分组条款。

数据库系统中有大量的数据。即使数据以适当的顺序以表格的形式排列，用户有时也希望将查询中的数据分组以便于访问。要以组的形式排列数据（列），必须在查询中使用名为 `group by` 的子句。`group by` 子句根据查询中指定的列排列数据。基本语法是：

## 语法

```sql
select select_list 
from table_name 
group by column_1, column_2 
```

下面给出了一个例子——学生表：

| Roll Number | Name | Course |
| :--- | :--- | :--- |
| 111 | Riya | SSE |
| 112 | Tanya | ECE |
| 113 | Minakshi | ME |
| 114 | Rita | BT |
| 115 | Sangeeta | CH |
| 116 | Deepa | EEE |

如果用户想要根据学号（`roll number`）对数据进行分组，可以按如下所示完成：

```sql
select name
from student 
group by roll number 
```

**输出：**

| Name | Roll Number |
| :--- | :--- |
| Riya | 111 |
| Tanya | 112 |
| Minakshi | 113 |
| Rita | 114 |
| Sangeeta | 115 |
| Deepa | 116 |

这样，可以使用 `group by` 子句对表进行分组。在实时生产中，`group by` 子句用于通过应用聚合函数（`MAX()`、`MIN()`等）来生成计算。用户经常混淆 `group by` 和 `order by` 子句。`Order by` 子句用于按时间顺序排列数据。`Group by` 子句用于以组的形式排列数据。

为了更好地理解，下面给出了一个例子。

| Roll Number | Name | Course |
| :--- | :--- | :--- |
| 111 | Riya | SSE |
| 112 | Tanya | ECE |
| 113 | Minakshi | ME |
| 114 | Rita | BT |
| 115 | Sangeeta | CH |
| 116 | Deepa | EEE |

## 使用 `order by` 和 `group by` 的查询

```sql
select roll number
from student 
order by name ASC 
```

**输出：**

| Roll Number | Name |
| :--- | :--- |
| 112 | Tanya |
| 116 | Deepa |
| 113 | Minakshi |
| 114 | Rita |
| 111 | Riya |
| 115 | Sangeeta |

```sql
select roll number
from student 
group by name 
```

**输出：**

| Roll Number | Name |
| :--- | :--- |
| 111 | Riya |
| 112 | Tanya |
| 113 | Minakshi |
| 114 | Rita |
| 115 | Sangeeta |
| 116 | Deepa |

从例子中，我们可以清楚地注意到 `group by` 子句和 `order by` 子句之间的区别。如果是按顺序排列，则名称按字母顺序（A-Z）排列。如果用户必须从 Z-A 安排，可以按如下方式进行。

```sql
select roll number
from student
order by name DESC
```

输出将安排如下：

| Roll Number | Name |
| :--- | :--- |
| 115 | Sangeeta |
| 111 | Riya |
| 114 | Rita |
| 113 | Minakshi |
| 116 | Deepa |
| 112 | Tanya |

这样，排列方式可以被修改。在 `group by` 的情况下，数据以组的形式排列，但不是按时间顺序排列。这里，没有使用 `where` 子句，因为它会产生错误。