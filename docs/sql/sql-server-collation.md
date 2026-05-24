# SQL Server 排序规则

> 原文:[https://www.geeksforgeeks.org/sql-server-collation/](https://www.geeksforgeeks.org/sql-server-collation/)

[SQL Server](https://www.geeksforgeeks.org/introduction-of-ms-sql-server/) 中的**排序规则**为数据提供排序规则、大小写和重音敏感性属性。排序规则定义了代表数据库元数据中每个字符的位模式。SQL Server 支持在数据库中存储具有不同排序规则的对象。

与排序规则相关的选项如下:

*   区分大小写(_CS)
*   区分重音(_AS)
*   区分假名(_KS)
*   宽度敏感(_WS)
*   变化敏感选择器(_VSS)a
*   二进制(_BIN)
*   二进制码点(_BIN2)

**注意:**
选择二进制(_BIN)或二进制码点(_BIN2)时，其他排序选项不可用。

要检查 SQL Server 实例的服务器排序规则，请使用以下命令:

```sql
SELECT SERVERPROPERTY('collation');
```

要查找 SQL Server 实例上可用的排序规则列表，请使用以下命令:

```sql
SELECT * FROM sys.fn_helpcollations();
```

**排序规则级别:**
SQL Server 支持以下级别的排序规则:

1.  **Server-level collations :**
    The default server collation is set during SQL Server setup, and it becomes default collation of system databases and user databases.

    将排序规则分配给服务器后，您只能通过导出所有数据库对象和数据、重建主数据库以及导入所有数据库对象和数据来更改它。创建新的数据库或数据库列后，您将能够指定所需的排序规则，而不是更改 SQL Server 实例的默认排序规则。

    要查找 SQL Server 的服务器级排序规则，请使用以下查询:

    ```sql
    SELECT CONVERT(varchar, SERVERPROPERTY('collation'));
    ```

2.  **Database-level collations :**
    The database collation is used for all metadata within database, and therefore collation is that default for all string columns, temporary objects, variable names, and other strings used in database. If no collation is defined while creating database, database will used default server collation.

    要创建具有排序规则的数据库，可以使用 create database 语句:

    **语法–**

    ```sql
    CREATE DATABASE databasename COLLATE collationtype;
    ```

    **示例:**

    ```sql
    CREATE DATABASE GeekDB COLLATE Greek_CS_AI; 
    ```

    要更改用户数据库的排序规则，可以使用 ALTER DATABASE 语句:

    **语法–**

    ```sql
    ALTER DATABASE databasename COLLATE collationtype;
    ```

    **注意:**只有更改服务器的排序规则，才能更改系统数据库的排序规则。

    **示例:**

    ```sql
    ALTER DATABASE GeekDB COLLATE SQL_Latin1_General_CP1_CI_AS; 
    ```

    **注意:**
    更改数据库级排序规则不会影响列级或表达式级排序规则。

3.  **Column-level collations :**
    While creating or altering table, one can specify collations for each character-string column by using COLLATE clause. If column collation is not specified, column is created with default collation of database.

    要更改列的排序规则，我们可以使用 ALTER TABLE 语句:

    **语法–**

    ```sql
    ALTER TABLE tablename 
    ALTER COLUMN columnnmae COLLATE collationtype;
    ```

    **示例:**

    ```sql
    ALTER TABLE Geektable 
    ALTER COLUMN namecol NVARCHAR(10) COLLATE Greek_CS_AI; 
    ```

4.  **Expression-level collations**
    Expression-level collations are used when statement is run, and they affect the way output is returned. This allows ORDER BY sort results to be specific.

    **语法–**

    ```sql
    SELECT * FROM tablename 
    ORDER BY columnname COLLATE collationtype;
    ```

    **示例:**

    ```sql
    SELECT * FROM Geektab 
    ORDER BY nname COLLATE SQL_Latin1_General_CP1_CI_AS; 
    ```