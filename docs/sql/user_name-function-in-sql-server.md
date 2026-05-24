# SQL Server 中的 USER_NAME()函数

> 原文:[https://www . geesforgeks . org/user _ name-function-in-SQL-server/](https://www.geeksforgeeks.org/user_name-function-in-sql-server/)

**USER_NAME() :**

SQL Server 中的这个函数用于返回基于所述 id 的数据库用户名。

**功能:**

*   This function is used to find the user name of the database used.
*   This function is an advanced function.
*   This function only accepts one parameter, namely the ID number.
*   If no ID number is specified, this function returns the name of the current user.

**语法:**

```sql
USER_NAME(id_number)
```

**参数:**

此方法只接受一个参数。

*   **ID number–** ID number specified in the user database. It is optional.

**返回:**

它返回指定 id 号的用户名。此外，如果没有指定 id 号，则返回当前用户名。

**示例-1 :**

使用 USER_NAME()函数并获取没有 id 号的用户名。

```sql
SELECT USER_NAME();
```

**输出:**

```sql
nidhi
```

这里不提供 id 号，所以返回当前用户的名字。

**示例-2 :**

使用 USER_NAME()函数并获取指定 id 号的用户名。

```sql
SELECT USER_NAME(2);
```

**输出:**

```sql
Geek
```

**示例-3 :**

使用 USER_NAME()函数，并使用变量获取指定 id 号的用户名。

```sql
DECLARE @id INT;
SET @id = 3;
SELECT USER_NAME(@id);
```

**输出:**

```sql
INFORMATION_SCHEMA
```

**示例-4 :**

使用 USER_NAME()函数，并使用 CAST()函数获取指定 id 号的用户名。

```sql
SELECT USER_NAME(CAST(2.2 as int));
```

**输出:**

```sql
Geek
```

**应用:**

该函数用于查找所用数据库的用户名。