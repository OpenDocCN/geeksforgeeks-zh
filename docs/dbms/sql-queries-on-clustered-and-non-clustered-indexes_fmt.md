# 聚集索引和非聚集索引上的 SQL 查询

> 原文：[https://www.geeksforgeeks.org/sql-queries-on-clustered-and-non-clustered-indexes/](https://www.geeksforgeeks.org/sql-queries-on-clustered-and-non-clustered-indexes/)

先决条件–[在数据库中建立索引](https://www.geeksforgeeks.org/indexing-in-databases-set-1/)

`建立索引`是一个从定义的表中更快地返回您请求的数据的过程。没有索引，SQL 服务器必须扫描整个表来查找您的数据。通过索引，当您通过检查索引页在书中搜索内容时，SQL server 会做完全相同的事情。同样，表的索引允许我们在不扫描整个表的情况下定位准确的数据。在 SQL 中有两种类型的索引。

1.  聚集索引
2.  非聚集索引

## 1. 聚集索引

聚集索引是一种建立行的物理排序顺序的索引类型。假设您有一个表 `Student_info`，该表包含 `ROLL_NO` 作为主键，而在该主键上自行创建的聚集索引将按照 `ROLL_NO` 对 `Student_info` 表进行排序。聚簇索引就像字典一样，在字典中排序顺序是按字母顺序排列的没有单独的索引页。

### 示例

```
Input:
CREATE TABLE Student_info
(
ROLL_NO int(10) primary key,
NAME varchar(20),
DEPARTMENT varchar(20),
);
insert into Student_info values(1410110405, 'H Agarwal', 'CSE') 
insert into Student_info values(1410110404, 'S Samadder', 'CSE')
insert into Student_info values(1410110403, 'MD Irfan', 'CSE')

SELECT * FROM Student_info 
```

### 输出

| ROLL_NO | NAME | DEPARTMENT |
| :--- | :--- | :--- |
| 1410110403 | MD Irfan | CSE |
| 1410110404 | S Samadder | CSE |
| 1410110405 | H Agarwal | CSE |

如果我们想在其他列上创建聚集索引，那么首先我们必须删除主键，然后我们可以删除以前的索引。

请注意，将列定义为主键会使该列成为该表的聚集索引。要创建任何其他列，聚集索引首先，我们必须按照下面的过程删除前一列。

### 语法

```
//Drop index
drop index table_name.index_name
//Create Clustered index index
create Clustered index IX_table_name_column_name 
             on table_name (column_name ASC)  
```

### 注意

我们只能在一个表中创建一个聚集索引。

## 2. 非聚集索引

非聚集索引是一种独立于存储在表中的数据的索引结构，它对一个或多个选定的列进行重新排序。创建非聚集索引是为了提高聚集索引未覆盖的常用查询的性能。这就像一本教科书，索引页是在那本书的开头单独创建的。

### 示例

```
Input: 
CREATE TABLE Student_info
(
ROLL_NO int(10),
NAME varchar(20),
DEPARTMENT varchar(20),
);
insert into Student_info values(1410110405, 'H Agarwal', 'CSE') 
insert into Student_info values(1410110404, 'S Samadder', 'CSE')
insert into Student_info values(1410110403, 'MD Irfan', 'CSE')

SELECT * FROM Student_info 
```

### 输出

| ROLL_NO | NAME | DEPARTMENT |
| :--- | :--- | :--- |
| 1410110405 | H Agarwal | CSE |
| 1410110404 | S Samadder | CSE |
| 1410110403 | MD Irfan | CSE |

### 注意

我们可以在一个表中创建一个或多个 `Non_Clustered` 索引。

### 语法

```
//Create Non-Clustered index
create NonClustered index IX_table_name_column_name 
      on table_name (column_name ASC) 
```

**Table: Student_info**

| ROLL_NO | NAME | DEPARTMENT |
| :--- | :--- | :--- |
| 1410110405 | H Agarwal | CSE |
| 1410110404 | S Samadder | CSE |
| 1410110403 | MD Irfan | CSE |

**输入:**
在 `Student_info` (`NAME` ASC)上创建非聚集索引 `IX_Student_info_NAME`

**输出:**

**Index**

| NAME | 行地址 |
| :--- | :--- |
| H Agarwal | 1 |
| MD Irfan | 3 |
| S Samadder | 2 |

## 聚集与非聚集索引的比较

*   一个表中只能有一个聚集索引，或者一个或多个非聚集索引。
*   在聚集索引中，没有单独的索引存储，但在非聚集索引中，索引有单独的索引存储。
*   聚集索引比非聚集索引慢。