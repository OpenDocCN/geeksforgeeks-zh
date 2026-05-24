# MySQL | DATABASE()和 CURRENT_USER()函数

> 原文:[https://www . geesforgeks . org/MySQL-database-current _ user-functions/](https://www.geeksforgeeks.org/mysql-database-current_user-functions/)

**数据库()功能**

MySQL 中的 DATABASE()函数返回默认或当前数据库的名称。DATABASE()函数返回的字符串或名称使用 utf8 字符集。如果没有默认数据库，数据库函数将返回空值。
在比 MySQL 4.1.1 旧的版本中，如果没有默认数据库，Database 函数用来返回空字符串。

**语法:**

```sql
SELECT DATABASE();
```

DATABASE()函数易于使用，不接受任何参数。我们可以在 MySQL 控制台上使用上面的语法轻松获得默认数据库的名称。

**示例:**
让我们考虑一下默认数据库的名称是“Employees”。因此要知道默认数据库的名称，可以通过以下方式执行数据库功能:

![](img/b9d2c92549792f4a728d741eb312493f.png)

**输出:**

```sql
'Employees'
```

**CURRENT_USER()功能**

MySQL 中的 CURRENT_USER()函数用于返回 MySQL 帐户的用户名和主机名，服务器使用该帐户对当前客户端进行身份验证。

从 MySQL 4.1 开始。，CURRENT_USER()函数使用 utf8 字符集。

**语法:**

```sql
SELECT CURRENT_USER();
```

CURRENT_USER()函数也不接受任何参数。

**示例:**
让我们考虑一下服务器用来验证当前客户端的 MySQL 帐户的用户名是“root”，主机名是“localhost”。因此，要知道服务器用来验证当前客户端的 MySQL 帐户的用户名和主机名，可以通过以下方式执行 CURRENT_USER()函数:

![](img/e873c144d867e38760d6ea66ed4e696c.png)

**输出:**

```sql
'root@localhost'
```