# SQL Server 中的 SESSION_USER()函数

> 原文:[https://www . geesforgeks . org/session _ user-function-in-SQL-server/](https://www.geeksforgeeks.org/session_user-function-in-sql-server/)

**SESSION_USER() :**

SQL Server 中的此函数用于返回正在使用的 SQL Server 数据库中的当前用户名。

**功能:**

*   This function is used to find the name of the current user.
*   This function is an advanced function.
*   The function does not accept any parameters.

**语法:**

```sql
SESSION_USER;
```

**参数:**

此方法不接受任何参数。

**返回:**

它返回正在使用的 SQL Server 数据库中的当前用户名。

**示例-1 :**

使用 SESSION_USER()函数并获取当前用户的名称。

```sql
SELECT SESSION_USER;
```

**输出:**

```sql
nidhi
```

**示例-2 :**

在下面的例子中使用 SESSION_USER 作为默认值并获得输出。

```sql
CREATE TABLE user01
(  
user_id int IDENTITY(100, 2) NOT NULL,
customer_id int NOT NULL,
user_name char(50) NOT NULL DEFAULT SESSION_USER
);  
INSERT user01(customer_id)  
VALUES (101);

INSERT user01(customer_id)  
VALUES (102);

SELECT * FROM user01;  
```

**输出:**

```sql
  | user_id  | customer_id | user_name
-----------------------------------------
1 | 100      | 101         | nidhi
-----------------------------------------
2 | 102      | 102         | nidhi
```

在这里，首先需要创建一个表，然后向其中插入值，然后使用 SESSION_USER 函数作为默认值生成所需的输出。

**注意:**对于运行上述代码使用 SQL server 编译器，也可以使用在线编译器。

**示例-3 :**

使用 SESSION_USER()函数并模拟用户“极客”。

```sql
SELECT SESSION_USER;  
EXECUTE AS USER = 'Geek';  
SELECT SESSION_USER;  
```

**输出:**

```sql
nidhi
Geek
```

这里，我们将用户模拟为“极客”，然后调用 SESSION_USER 函数来获取当前用户的名称。

**示例-4 :**

使用 SESSION_USER()函数模拟用户“极客”，然后再次恢复代码以获得以前的当前用户。

```sql
SELECT SESSION_USER;  
EXECUTE AS USER = 'Geek';  
SELECT SESSION_USER;  
REVERT;
SELECT SESSION_USER;
```

**输出:**

```sql
nidhi
Geek
nidhi
```

**应用:**

该函数用于在 SQL server 的数据库中查找当前用户名。