# MS SQL Server 中的完全连接和内部连接

> 原文：[https://www.geeksforgeeks.org/full-join-and-inner-join-in-ms-sql-server/](https://www.geeksforgeeks.org/full-join-and-inner-join-in-ms-sql-server/)

先决条件 – [MS SQL Server 简介](https://www.geeksforgeeks.org/introduction-of-ms-sql-server/)

## 1. 完全连接
完全连接选择左右表中的所有行以及匹配的行。如果没有匹配的行，它将显示为空。

### 语法
```sql
select select_list 
from table1 full join table2 on join_predicate
```
或者
```sql
select * 
from table1 full join table2
```

## 2. 内部连接
内部连接从左右表中检索匹配的行。如果没有匹配的行，将显示空值。

### 语法
```sql
select select_list 
from table1 inner join table2 on join_predicate
```
或者
```sql
select * 
from table1 inner join table2 
```

### 注意
这些连接可以应用于多个表。

### 示例
下面给出了大学数据库中的两个表，即学生表和分数表。

**Table – Student**

| 名字 | RollNo | 年龄 | 课程 |
| :--- | :--- | :--- | :--- |
| Aila | 111 | 19 | 十年级 |
| Bablu | 112 | 18 | 十一年级 |
| Chintu | 113 | 19 | 十二年级 |
| Nina | 114 | 18 | 十年级 |

**Table – Mark**

| 名字 | RollNo | 课程 | 平均绩点 |
| :--- | :--- | :--- | :--- |
| Aila | 111 | 十年级 | 9.6 |
| Bablu | 112 | 十一年级 | 9.5 |
| Chintu | 113 | 十二年级 | 7.7 |
| Nina | 114 | 十年级 | 7.5 |

### 1. 完全连接
完全连接应用于学生和分数表，下表是结果集。

```sql
select * 
from student full join marks 
```

| 名字 | RollNo | 年龄 | 课程 | 平均绩点 |
| :--- | :--- | :--- | :--- | :--- |
| Aila | 111 | 19 | 十年级 | 9.6 |
| Bablu | 112 | 18 | 十一年级 | 9.5 |
| Chintu | 113 | 19 | 十二年级 | 7.7 |
| Nina | 114 | 18 | 十年级 | 7.5 |

### 2. 内部连接
内部连接应用于学生表和成绩表，下表是结果集。

```sql
select * 
from student inner join marks 
```

| 名字 | RollNo | 课程 |
| :--- | :--- | :--- |
| Aila | 111 | 十年级 |
| Bablu | 112 | 十一年级 |
| Chintu | 113 | 十二年级 |
| Nina | 114 | 十年级 |