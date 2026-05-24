# 在 SQL Server 中删除登录

> 原文:[https://www.geeksforgeeks.org/drop-login-in-sql-server/](https://www.geeksforgeeks.org/drop-login-in-sql-server/)

**DROP LOGING**语句可用于删除用于连接到 SQL Server 实例的用户或登录名。

**语法–**

```sql
DROP LOGIN loginname;
GO 
```

**权限:**
删除登录的用户必须在服务器上拥有 ALTER ANY LOGIN 权限。

**注意–**
当前登录到 SQL Server 的登录无法删除。

如果您尝试删除当前使用 SQL Server 的登录名，drop login 语句将引发以下错误。

登录“登录名”删除失败

让我们假设，我们已经创建了以下登录:

```sql
CREATE LOGIN geeks  
WITH PASSWORD = ‘gEe@kF0rG##ks’; 
```

下面的例子展示了如何在 SQL Server 中使用 DROP LOGIN 语句。

**示例–**

```sql
DROP LOGIN geeks; 
```

上例中使用的 DROP LOGIN 将从 SQL server 中删除名为 geeks 的登录。这个 DROP LOGIN 语句只有在极客不是当前用户的情况下才会运行。