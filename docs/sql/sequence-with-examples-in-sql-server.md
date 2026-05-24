# SQL Server 中的示例序列

> 原文:[https://www . geesforgeks . org/sequence-with-examples-in-SQL-server/](https://www.geeksforgeeks.org/sequence-with-examples-in-sql-server/)

**[序列](https://www.geeksforgeeks.org/sql-sequences/) :**
序列是数字的列表，以有序的方式排列。例如，{1，2，3}是一个序列，{3，2，1}也是一个序列，但序列不同。

它是一个用户定义的模式对象，根据 SQL server 中的指定值生成一个数字列表。

**语法:**

```sql
CREATE SEQUENCE schema_name.sequence_name  
AS integer_type 
START WITH start_value
INCREMENT BY increment_value 
MINVALUE min_value 
MAXVALUE max_value ;

```

**使用的参数:**

*   **序列名称–**
    为序列定义一个在数据库中唯一的名称。
*   **AS integer _ type–**
    使用任意整数类型的序列为例；TINYINT、INT 或 DECIMAL。默认情况下，序列使用 BIGINT。
*   **从 start_value 开始–**
    定义序列的第一个值。
*   **INCREMENT BY increment_value–**
    定义序列对象的 increment_value 调用 NEXT VALUE FOR 函数，INCREMENT _ VALUE 不能为零。
*   **最小值最小值–**
    定义序列的下限值。
*   **最大值最大值–**
    定义序列的上限值。

使用以下语句获取 SQL server 中序列的详细信息:

```sql
SELECT * 
FROM sys.sequences; 
```

**示例-1 :** 创建简单序列

```sql
CREATE SEQUENCE geeks_num
AS INT
START WITH 10
INCREMENT BY 10; 
```

**输出–**

```sql
SELECT NEXT VALUE FOR geeks_num; 
```

| 当前值 |
| --- |
| Ten |

(1 行受影响)

再次运行以下语句，geeks_num 的值将增加 10。

```sql
SELECT NEXT VALUE FOR geeks_num; 
```

**输出–**

| 当前值 |
| --- |
| Twenty |

(1 行受影响)

**示例-2 :** 在表中使用序列对象。
让我们创建一个名为 geeksch 的模式:

```sql
CREATE SCHEMA geeksch;
GO 
```

并创建一个名为 geektab 的新表:

```sql
CREATE TABLE geeksch.geektab
(
geek_id INT PRIMARY KEY, 
DOJ date NOT NULL 
); 
```

现在，创建一个名为 geek_number 的序列，该序列以 1 开始并增加 1。

```sql
CREATE SEQUENCE geeksch.geek_number 
AS INT
START WITH 1
INCREMENT BY 1; 
```

向 geeksch.geektab 表中插入行，并按 geeksch.geek_number 顺序使用值:

```sql
INSERT INTO geeksch.geektab(g_id, DOJ)
VALUES(NEXT VALUE FOR geeksch.geek_number, '2019-07-15');

INSERT INTO geeksch.geektab(g_id, DOJ)
VALUES(NEXT VALUE FOR geeksch.geek_number, '2018-04-10'); 
```

要查看 geeksch.geektab 表的值:

```sql
SELECT * FROM  geeksch.geektab; 
```

**输出–**

| g_id | (美)司法部(Department of Justice) |
| --- | --- |
| one | 2019-07-15 |
| Two | 2018-04-10′ |

**示例-3 :** 在多个表中使用序列对象示例。

```sql
CREATE SEQUENCE geeksch.g_no
START WITH 1
INCREMENT BY 1; 
```

使用 geeksch 序列创建表格。

```sql
CREATE TABLE geeksch.table1
(id INT PRIMARY KEY
DEFAULT (NEXT VALUE FOR geeksch.g_no),
DOJ DATE NOT NULL,
City NVARCHAR(100) ); 
```

这里，表有一个列 id，它的值是从 geeksch.g_no 序列中派生出来的。

```sql
INSERT INTO geeksch.table1(DOJ, City )
VALUES('2019-05-12', 'Delhi');

INSERT INTO geeksch.table1(DOJ, City )
VALUES(  '2019-06-18',  'Delhi'); 
```

使用 geeksch 序列创建另一个表。

```sql
CREATE TABLE geeksch.table2
(id INT PRIMARY KEY
DEFAULT (NEXT VALUE FOR geeksch.g_no), 
DOJ DATE NOT NULL, 
City NVARCHAR(100) ); 
```

这里，表有一个列 id，它的值是从 geeksch.g_no 序列中派生出来的。

让我们在表 2 中插入一些没有 id 列值的行:

```sql
INSERT INTO geeksch.table2(DOJ, City )
VALUES('2020-02-03','Noida');

INSERT INTO geeksch.table2(DOJ, City )
VALUES('2020-03-14','Noida'); 
```

**输出–**

```sql
SELECT * 
FROM geeksch.table1; 
```

**输出–**

| 身份证明（identification） | (美)司法部(Department of Justice) | 城市 |
| --- | --- | --- |
| one | 2019-05-12′ | 德里 |
| Two | 2019-06-18 | 德里 |

```sql
SELECT * 
FROM geeksch.table2; 
```

| 身份证明（identification） | (美)司法部(Department of Justice) | 城市 |
| --- | --- | --- |
| three | 2020-02-03 | 无聊死了 |
| four | 2020-03-14 | 无聊死了 |