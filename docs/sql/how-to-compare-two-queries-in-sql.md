# 如何在 SQL 中比较两个查询

> 原文:[https://www . geesforgeks . org/如何比较 sql 中的两个查询/](https://www.geeksforgeeks.org/how-to-compare-two-queries-in-sql/)

**SQL 中的查询:**
一个查询要么是邀请您提供信息中的数据结果，要么是邀请您对信息采取行动，或者是每一个。一个问题将为您提供一个简单问题的解决方案，执行计算，混合来自完全不同的表的数据，添加、更改或删除 info 中的数据。

**创建数据库:**
我们使用 **CREATE DATABASE** 命令创建一个新的 SQL 数据库。

**语法–**

> CREATE DATABASE db _ name

**在已创建的数据库中创建表:**
我们使用**创建表**命令创建一个新的 SQL 数据库。

**语法–**

> CREATE TABLE table_name (
> 列 1 数据类型、
> 列 2 数据类型、
> 列 3 数据类型、
> T4)；

**将值插入到创建的表中:**
我们使用**插入到**命令创建一个新的 SQL 数据库。

**语法–**

> 插入表名
> 值(值 1、值 2、值 3)；

**创建数据库和表的示例代码–**

## 服务器端编程语言（Professional Hypertext Preprocessor 的缩写）

```sql
CREATE DATABASE myDatabase;

CREATE TABLE myTable
(
Pid int,
FName varchar(255),
LName varchar(255),
Adrs varchar(255),
District varchar(255)
);

INSERT INTO myTable (Pid, FName, LName, Adrs, District)
VALUES ('1','Krishna','Kripa','Jansa','Varanasi');
```

#### 输出–

<figure class="table">

| **我的数据库:我的表格**

 |
| **Pid** | fname | lname | **Adrs** | **区** |
| one | 克利须那 | 克里帕 | 珍莎 | 瓦拉纳西 |

</figure>

**查询比较:**
例如，我们在完全不同的数据库中有两个相似的表，我们希望了解其中的不同之处。以下是制作示例数据库、表和信息的脚本。

## 服务器端编程语言（Professional Hypertext Preprocessor 的缩写）

```sql
CREATE DATABASE myDatabase1;
GO
USE myDatabase1;
GO

CREATE TABLE myTable
(
Aid int,
Atype varchar(10),
Acost varchar(10)
);

GO

INSERT INTO myTable (Aid, Atype, Acost)
  VALUES ('001', '1', '40'),
  ('002', '2', '80'),
  ('003', '3', '120')
GO

CREATE DATABASE myDatabase2;
GO
USE myDatabase2;
GO

CREATE TABLE myTable
(
Aid int,
Atype varchar(10),
Acost varchar(10)
);

GO

INSERT INTO myTable (Aid, Atype, Acost)
  VALUES ('001', '1', '40'),
  ('002', '2', '80'),
  ('003', '3', '120'),
  ('004', '4', '160')

GO
```

**输出─**
用于我的数据库 1】

<figure class="table">

**【aid】**

|  |  |

</figure>

对于我的数据库 2──

**【attype】**

| **援助** |

**使用 EXCEPT 关键字比较表中的 SQL 查询:**
**EXCEPT** 显示了两个表之间的区别。人们习惯于比较两张表之间的差异。

现在运行这个查询，其中我们在 DB1 的 DB2 上使用了 EXCEPT 关键字–

## 服务器端编程语言（Professional Hypertext Preprocessor 的缩写）

```sql
SELECT * FROM myDatabase2.myTable
EXCEPT
SELECT * FROM myDatabase1.myTable
```

#### 输出–

<figure class="table">

| **援助** | **attype** | **方法** |
| 004 | four | One hundred and sixty |

</figure>