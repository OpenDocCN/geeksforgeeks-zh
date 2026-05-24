# 在 SQL Server 中创建模式

> 原文:[https://www.geeksforgeeks.org/create-schema-in-sql-server/](https://www.geeksforgeeks.org/create-schema-in-sql-server/)

一个**模式**是一个数据库对象的集合，如表、触发器、存储过程等。模式与称为模式所有者的用户相关联。数据库可能有一个或多个架构。

[SQL Server](https://www.geeksforgeeks.org/sql-tutorial/#sql-server) 有一些内置的模式，例如:dbo、guest、sys 和 INFORMATION_SCHEMA。

dbo 是新数据库的默认模式，由 dbo 用户拥有。使用 CREATE USER 命令创建新用户时，用户将使用 dbo 作为其默认模式。

CREATE SCHEMA 语句用于在当前数据库中创建新的架构。

**语法:**

```sql
CREATE SCHEMA schemaname
   [AUTHORIZATION ownername]
GO
```

**示例–**

```sql
CREATE SCHEMA geeks_sch;
GO 
```

**要选择 SQL Server SCHEMA :**
要列出当前数据库中的所有模式，请使用如下所示的查询:

```sql
SELECT  *
FROM sys.schemas 
```

**结果–**

<center>

| 名字 | 架构 id | 主体 _id |
| --- | --- | --- |
| dbo | one | one |
| 客人 | Two | Two |
| 信息 _ 架构 | three | four |
| [计]系统复制命令（system 的简写） | four | four |
| db_owner | Sixteen thousand three hundred and eighty-four | Sixteen thousand three hundred and eighty-four |
| S7-1200 可编程控制器 | Sixteen thousand three hundred and eighty-five | Sixteen thousand three hundred and eighty-five |
| db_securityadmin | Sixteen thousand three hundred and eighty-six | Sixteen thousand three hundred and eighty-six |
| S7-1200 可编程控制器 | Sixteen thousand three hundred and eighty-seven | Sixteen thousand three hundred and eighty-seven |
| db_backupoperator | Sixteen thousand three hundred and eighty-nine | Sixteen thousand three hundred and eighty-nine |
| db_datareader | Sixteen thousand three hundred and ninety | Sixteen thousand three hundred and ninety |
| db_datawriter | Sixteen thousand three hundred and ninety-one | Sixteen thousand three hundred and ninety-one |
| S7-1200 可编程控制器 | Sixteen thousand three hundred and ninety-two | Sixteen thousand three hundred and ninety-two |
| db_denydatawriter | Sixteen thousand three hundred and ninety-three | Sixteen thousand three hundred and ninety-three |

</center>

**为模式创建对象:**
要在 geeks_sch 模式中创建新的名为 Geektab 的表:

**语法:**

```sql
CREATE TABLE schemaname.tablename(
 values... );
```

**示例–**

```sql
CREATE TABLE geeks_sch.Geektab(
G_id INT PRIMARY KEY IDENTITY, 
Name VARCHAR(200), 
DOJ DATETIME2 NOT NULL
); 
```