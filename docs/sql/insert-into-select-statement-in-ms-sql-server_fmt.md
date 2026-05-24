# 插入到 MS SQL Server 的选择语句中

> 原文: [https://www.geeksforgeeks.org/insert-into-select-statement-in-ms-sql-server/](https://www.geeksforgeeks.org/insert-into-select-statement-in-ms-sql-server/)

先决条件 – [`INSERT`语句 in MS SQL Server](https://www.geeksforgeeks.org/insert-statement-in-ms-sql-server/)、[`SELECT`语句 in MS SQL Server](https://www.geeksforgeeks.org/select-statement-in-ms-sql-server/)

考虑一个大学数据库。有两张表，即`Student`表和`Marks`表。在这种情况下，少数学生的分数要从`Marks`表转移到`Student`表，有很多种方法。

可以使用子查询（嵌套在另一个查询中的查询），但这是一个复杂且耗时的过程。

`INSERT INTO SELECT`语句使工作更加容易。此语句用于从其他表中插入数据。

## 语法

```sql
INSERT [TOP(exp)[PERCENT]]
INTO target_table
column_list
query
```

## 示例

**Table –** Student

| Roll No | Name | Course |
| --- | --- | --- |
| 111 | Riya | SSE |
| 112 | Tanya | ECE |
| 113 | Minakshi | ME |
| 114 | Rita | BT |
| 115 | Indrani | CH |
| 116 | Dipa | EME |

**Table –** Marks

| Roll No | Name | GPA |
| --- | --- | --- |
| 111 | Riya | 9.5 |
| 112 | Tanya | 9.4 |
| 113 | Minakshi | 8.7 |
| 114 | Rita | 8.1 |
| 115 | Indrani | 7.7 |
| 116 | Dipa | 7.1 |

如果用户想将标记转移到学生表，查询如下：

```sql
INSERT INTO Marks (Roll_No, Name, GPA)
SELECT Roll_No, Name, Course 
FROM Student 
```

值被插入。为了验证，查询如下：

```sql
SELECT *
FROM Student 
```

**输出：**

| Roll No | Name | Course | Average_Marks |
| --- | --- | --- | --- |
| 111 | Riya | SSE | 9.5 |
| 112 | Tanya | ECE | 9.4 |
| 113 | Minakshi | ME | 8.7 |
| 114 | Rita | BT | 8.1 |
| 115 | Indrani | CH | 7.7 |
| 116 | Dipa | EME | 7.1 |

这是插入值的另一种方式。通过使用`TOP`关键字，我们可以从表中提取所需的值：

```sql
INSERT TOP (6) PERCENT
INTO Marks(Roll_No, Name, GPA)
SELECT Roll_No, Name, Course 
FROM Student 
ORDER BY Roll_No 
```

**输出：**

| Roll No | Name | Course | Average_Marks |
| --- | --- | --- | --- |
| 111 | Riya | SSE | 9.5 |
| 112 | Tanya | ECE | 9.4 |
| 113 | Minakshi | ME | 8.7 |
| 114 | Rita | BT | 8.1 |
| 115 | Indrani | CH | 7.7 |
| 116 | Dipa | EME | 7.1 |

查询中略有不同，但我们得到了相同的结果集。`TOP`是可选的，当用户只想从表中提取特定数量的行时，可以使用它。