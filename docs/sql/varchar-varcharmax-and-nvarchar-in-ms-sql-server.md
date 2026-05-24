# MS SQL Server 中的 varchar、varchar(最大值)和 nvarchar

> 原文:[https://www . geesforgeks . org/varchar-varcharmax-and-nvarchar-in-ms-SQL-server/](https://www.geeksforgeeks.org/varchar-varcharmax-and-nvarchar-in-ms-sql-server/)

我们知道一个数据库可以有不同的数据类型。考虑一个拥有各种数据库的组织，如员工、部门、财务。员工数据库有一个存储每个员工详细信息的表，员工是使用员工标识唯一标识的。

在大多数情况下，员工 ID 由数字和字母组合而成。数据库如何存储这些值？它使用一种特殊的数据类型，称为可变字符或可变字符数据类型。它使用数字和字母。

1.  **varchar :**
    Variable Character or varchar for short is a datatype that stores non-Unicode data.
    The syntax for varchar is:
    **Syntax :**

    ```sql
    varchar (n)

    ```

    **n–**是字节数。最大存储容量可达 8000 字节。

2.  **varchar(max) :**
    它存储最大存储大小为 2 -1 字节的字符串数据。

**语法:**

```sql
varchar(max)

```

7.  **nvarchar :**
    This stores variable length unicode data.
    Syntax for nvarchar is:
    **Syntax :**

    ```sql
    nvarchar

    ```

    **n–**为字节数，最多可存储 4000 字节。如果没有指定数据类型的长度，它将采用默认值 1。创建表时可以使用这些数据类型。

**这些数据类型的概述:**

<center>

| 特征 | 可变长字符串 | varchar(最大值) | nvarchar |
| 储存；储备 | 它存储可变长度的非 unicode 字符串数据。 | 它存储可变长度的非 unicode 字符串数据。 | 它存储可变长度的 unicode 字符串数据。 |
| 句法 | varchar(n)**n 为字节数* | varchar(max)**max 为最大存储值。* | nvarchar**n 为字节数。* |
| 存储大小 | 1-8000 字节 | 2 -1 字节 | 1-4000 字节 |

</center>