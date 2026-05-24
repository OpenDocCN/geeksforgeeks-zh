# MySQL 中的 SYSTEM_USER()函数

> 原文:[https://www . geesforgeks . org/system _ user-function-in-MySQL/](https://www.geeksforgeeks.org/system_user-function-in-mysql/)

**SYSTEM_USER() :**
这个函数帮助返回当前 MySQL 用户的用户名和主机名。函数不需要传递任何参数。

将返回的用户名是连接到服务器时用户指定的名称。主机名将是用户所连接的客户端主机的名称。

**注–**
函数 SYSTEM_USER()和 SESSION_USER()几乎相似。

**语法:**

```sql
SYSTEM_USER()
```

**参数:**
这个函数不需要传递任何参数或参数。

**返回:**
该函数将返回当前 MySQL 用户的用户名和主机名。

**支持的 MySQL 版本:**

*   MySQL 5.7
*   MySQL 5.6
*   MySQL 5.5
*   MySQL 5.1
*   MySQL 5.0
*   MySQL 4.1
*   MySQL 4.0
*   MySQL 3.23

**示例:**
在 MySQL 中实现 SYSTEM_USER()函数如下。
**语法–**

```sql
SELECT SYSTEM_USER();
```

**输出:**

```sql
//Expected Output will be in this format.
username@hostname
```

现在，让我们看看这个例子。

```sql
SELECT SYSTEM_USER();
```

**输出:**

```sql
author@gfg
```