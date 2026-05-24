# SQL Server 中的 SYSTEM_USER()函数

> 原文:[https://www . geesforgeks . org/system _ user-function-in-SQL-server/](https://www.geeksforgeeks.org/system_user-function-in-sql-server/)

**SYSTEM_USER()函数:**
这个函数在 SQL Server 中用来返回当前用户的登录名。

**特征:**

*   此功能用于查找当前用户的登录名。
*   该功能属于高级功能。
*   这个函数不接受任何参数。

**语法:**

```sql
SYSTEM_USER;
```

**参数:**
此方法不接受任何参数。

**返回:**
返回当前用户的登录名。

**示例-1 :**
使用 SYSTEM_USER()函数，获取当前用户的登录名。

```sql
SELECT SYSTEM_USER;
```

**输出:**

```sql
nidhi
```

**示例-2 :**
在下面的示例中使用 SYSTEM_USER 作为默认值并获取输出。

```sql
CREATE TABLE user01
(  
user_id int IDENTITY(100, 2) NOT NULL,
customer_id int NOT NULL,
user_name char(50) NOT NULL DEFAULT SYSTEM_USER
);  
INSERT user01(customer_id)  
VALUES (101);

INSERT user01(customer_id)  
VALUES (102);

SELECT * FROM user01; 
```

**输出:**

| s。没有。 | 【用户 _ id】 | 【客户 _ id】 | 【用户名】 |

在这里，首先需要创建一个表，然后将值插入其中，然后使用 SYSTEM_USER 函数作为默认值生成所需的输出。

**注意:**对于运行以上代码使用 sql server 编译器，也可以使用在线编译器。

**示例-3 :**
使用 SYSTEM_USER()函数，模拟用户‘极客’。

```sql
SELECT SYSTEM_USER;  
EXECUTE AS USER = 'Geek';  
SELECT SYSTEM_USER;  
```

**输出:**

```sql
nidhi
Geek
```

这里，我们将用户模拟为“极客”，然后调用 SYSTEM_USER 函数来获取当前用户的名称。

**示例-4 :**
使用 SYSTEM_USER()函数模拟用户‘Geek’，然后再次还原代码，得到上一个当前用户。

```sql
SELECT SYSTEM_USER;  
EXECUTE AS USER = 'Geek';  
SELECT SYSTEM_USER;  
REVERT;
SELECT SYSTEM_USER;
```

**输出:**

```sql
nidhi
Geek
nidhi
```

**应用:**
该功能用于查找当前用户的登录名。