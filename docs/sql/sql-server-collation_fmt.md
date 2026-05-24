# SQL Server 排序规则

> 原文:[https://www.geeksforgeeks.org/sql-server-collation/](https://www.geeksforgeeks.org/sql-server-collation/)

在 [SQL Server](https://www.geeksforgeeks.org/introduction-of-ms-sql-server/) 中，排序规则为数据提供排序规则、大小写和重音敏感性属性。排序规则定义了代表数据库元数据中每个字符的位模式。SQL Server 支持在数据库中存储具有不同排序规则的对象。

与排序规则相关的选项如下:

*   区分大小写(`_CS`)
*   区分重音(`_AS`)
*   区分假名(`_KS`)
*   宽度敏感(`_WS`)
*   变化敏感选择器(`_VSS`)
*   二进制(`_BIN`)
*   二进制码点(`_BIN2`)

注意:
选择二进制(`_BIN`)或二进制码点(`_BIN2`)时，其他排序选项不可用。

要检查 SQL Server 实例的服务器排序规则，请使用以下命令:

```sql
SELECT SERVERPROPERTY('collation');
```

要查找 SQL Server 实例上可用的排序规则列表，请使用以下命令:

```sql
SELECT * FROM sys.fn_helpcollations();
```

## 排序规则级别

SQL Server 支持以下级别的排序规则:

### 1. Server-level collations

默认服务器排序规则在 SQL Server 安装过程中设置，它成为系统数据库和用户数据库的默认排序规则。

将排序规则分配给服务器后，您只能通过导出所有数据库对象和数据、重建主数据库以及导入所有数据库对象和数据来更改它。创建新的数据库或数据库列后，您将能够指定所需的排序规则，而不是更改 SQL Server 实例的默认排序规则。

要查找 SQL Server 的服务器级排序规则，请使用以下查询:

```sql
SELECT CONVERT(varchar, SERVERPROPERTY('collation'));
```

### 2. Database-level collations

数据库排序规则用于数据库中的所有元数据，因此该排序规则是所有字符串列、临时对象、变量名以及数据库中使用的其他字符串的默认排序规则。如果在创建数据库时未定义排序规则，数据库将使用默认的服务器排序规则。

要创建具有排序规则的数据库，可以使用 `create database` 语句:

语法:

```sql
CREATE DATABASE databasename COLLATE collationtype;
```

示例:

```sql
CREATE DATABASE GeekDB COLLATE Greek_CS_AI; 
```

要更改用户数据库的排序规则，可以使用 `ALTER DATABASE` 语句:

语法:

```sql
ALTER DATABASE databasename COLLATE collationtype;
```

注意: 只有更改服务器的排序规则，才能更改系统数据库的排序规则。

示例:

```sql
ALTER DATABASE GeekDB COLLATE SQL_Latin1_General_CP1_CI_AS; 
```

注意:
更改数据库级排序规则不会影响列级或表达式级排序规则。

### 3. Column-level collations

在创建或更改表时，可以使用 `COLLATE` 子句为每个字符串列指定排序规则。如果未指定列排序规则，则使用数据库的默认排序规则创建列。

要更改列的排序规则，我们可以使用 `ALTER TABLE` 语句:

语法:

```sql
ALTER TABLE tablename 
ALTER COLUMN columnnmae COLLATE collationtype;
```

示例:

```sql
ALTER TABLE Geektable 
ALTER COLUMN namecol NVARCHAR(10) COLLATE Greek_CS_AI; 
```

### 4. Expression-level collations

表达式级排序规则在语句运行时使用，它们影响输出返回的方式。这允许 `ORDER BY` 对结果进行特定排序。

语法:

```sql
SELECT * FROM tablename 
ORDER BY columnname COLLATE collationtype;
```

示例:

```sql
SELECT * FROM Geektab 
ORDER BY nname COLLATE SQL_Latin1_General_CP1_CI_AS; 
```