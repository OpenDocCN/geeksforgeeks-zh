# 检查 SQL Server 数据库中是否存在表

> 原文:[https://www . geesforgeks . org/check-a-table-in-SQL-server-database-or-not/](https://www.geeksforgeeks.org/check-whether-a-table-exists-in-sql-server-database-or-not/)

在创建表之前，最好检查该表是否存在于 SQL Server 数据库中。

**备选项 1 :**
使用 OBJECT_ID 和 IF ELSE 语句检查表是否存在。

**查询:**

```sql
USE [DB_NAME]
GO
IF OBJECT_ID('table_name', 'U') IS NOT NULL
BEGIN
PRINT 'Table exists.'
END
ELSE
BEGIN
PRINT 'Table does not exist.'
END

```

**备选方案 2 :**
使用 INFORMATION_SCHEMA。用于检查表是否存在的运算符。

**查询:**

```sql
USE [DB_NAME]
GO
IF EXISTS (SELECT * FROM INFORMATION_SCHEMA.TABLES
WHERE TABLE_NAME = N'table_name')
BEGIN
PRINT 'Table exists.'
END
ELSE
BEGIN
PRINT 'Table does not exist.'
END

```

**备选方案 3 :**
使用 sys。对象来检查 SQL Server 中是否存在表。

**查询:**

```sql
USE [DB_NAME]
GO
IF EXISTS(SELECT 1 FROM sys.Objects
WHERE Object_id = OBJECT_ID(N'table_name')
AND Type = N'U')
BEGIN
PRINT 'Table exists.'
END
ELSE
BEGIN
PRINT 'Table does not exist.'
END

```

**输出:**

```sql
Table does not exists.
```

**备选方案 4 :**
使用 sys。检查表是否存在。

**查询:**

```sql
USE [DB_NAME]
GO
IF EXISTS(SELECT 1 FROM sys.Tables
WHERE Name = N'table_name')
BEGIN
PRINT 'Table exists.'
END
ELSE
BEGIN
PRINT 'Table does not exist.'
END

```

**示例:**
让我们假设我们有数据库名“ **SQL_DBA** ”并且我们需要创建一个新表“**geek _ demo**”–

**输入-1 :**

```sql
USE [SQL_DBA]
GO
IF OBJECT_ID('geek_demo', 'U') IS NOT NULL
BEGIN
PRINT 'Table exists.'
END
ELSE
BEGIN
PRINT 'Table does not exist.'
END

```

**输出-1 :**

```sql
Table does not exists.
```

让我们创建表格。

```sql
Create table geek_demo (id int, name varchar(200));
```

现在，让我们检查表是否已创建–

**输入-2 :**

```sql
USE [DB_NAME]
GO
IF EXISTS(SELECT 1 FROM sys.Objects
WHERE Object_id = OBJECT_ID(N'table_name')
AND Type = N'U')
BEGIN
PRINT 'Table exists.'
END
ELSE
BEGIN
PRINT 'Table does not exist.'
END

```

**输出-2 :**

```sql
Table exists.
```