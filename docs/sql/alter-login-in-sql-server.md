# 在 SQL Server 中更改登录

> 原文:[https://www.geeksforgeeks.org/alter-login-in-sql-server/](https://www.geeksforgeeks.org/alter-login-in-sql-server/)

**Alter login** 语句可用于更改 SQL Server 登录帐户的属性。

**语法:**

```sql
ALTER LOGIN loginname;
GO

```

启用禁用的登录–

**语法:**

```sql
ALTER LOGIN loginname ENABLE;

```

**示例–**

ALTER LOGIN geeks ENABLE

**更改登录密码**
**语法:**

```sql
ALTER LOGIN geeks WITH PASSWORD = 'newpassword';

```

**示例–**

```sql
ALTER LOGIN geeks WITH PASSWORD = ‘G9h$fm@1LZe’;

```

使用相同的登录名登录时，更改登录名的密码

**语法:**

```sql
ALTER LOGIN loginname 
WITH PASSWORD = 'newpassword' OLD_PASSWORD = 'oldpassword';

```

**示例–**

```sql
ALTER LOGIN geeks 
WITH PASSWORD = ‘G9h$fm@1LZe’ OLD_PASSWORD = ‘Ge@@k$s12’;

```

更改登录名

**语法:**

```sql
ALTER LOGIN loginnmae WITH NAME = newname;

```

**示例–**

```sql
ALTER LOGIN geeks WITH NAME = geek;

```

解锁登录

**语法:**

```sql
ALTER LOGIN loginnmae WITH PASSWORD = 'password' UNLOCK ;

```

**示例–**

```sql
ALTER LOGIN geeks WITH PASSWORD = ‘G9h$fm@1LZe’ UNLOCK ;

```

无需更改密码即可解锁登录

**语法:**

```sql
ALTER LOGIN [loginname] WITH CHECK_POLICY = OFF;
ALTER LOGIN [loginnmae] WITH CHECK_POLICY = ON;

```

**示例–**

```sql
ALTER LOGIN geeks WITH CHECK_POLICY = OFF;

ALTER LOGIN geeks WITH CHECK_POLICY = ON;

```