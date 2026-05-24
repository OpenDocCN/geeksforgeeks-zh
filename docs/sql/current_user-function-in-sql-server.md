# SQL Server 中的 CURRENT_USER()函数

> 原文:[https://www . geesforgeks . org/current _ user-function-in-SQL-server/](https://www.geeksforgeeks.org/current_user-function-in-sql-server/)

**CURRENT_USER()函数:**
SQL Server 中的这个函数用来返回当前用户在使用中的 SQL Server 的数据库中的名字。

**特征:**

*   此功能用于查找当前用户的姓名。
*   该功能属于高级功能。
*   这个函数不接受任何参数。

**语法:**

```sql
CURRENT_USER
```

**参数:**此方法不接受任何参数。

**返回:**返回正在使用的 SQL Server 数据库中当前用户的名称。

**示例-1 :**
使用 CURRENT_USER()函数，获取当前用户的姓名。

```sql
SELECT CURRENT_USER;
```

**输出:**

```sql
nidhi
```

**示例-2 :**
在下面的示例中使用 CURRENT_USER 作为默认值并获取输出。

```sql
CREATE TABLE user01 (  
user_id int IDENTITY(100, 2) NOT NULL,
customer_id int NOT NULL,
user_name char(50) NOT NULL DEFAULT CURRENT_USER
); 
```

在表格中插入值–

```sql
INSERT user01(customer_id)  
VALUES (101), (102);
```

显示表格的内容–

```sql
SELECT * 
FROM user01;  
```

**输出:**

<figure class="table">

|  | 【用户 _ id】 | 【客户 _ id】 | 【用户名】 |

</figure>

在这里，首先需要创建一个表，然后将值插入其中，然后使用 CURRENT_USER 函数作为默认值生成所需的输出。

**注意:**对于使用 SQL server 编译器运行上述代码，也可以使用在线编译器。

**示例-3 :**
使用 CURRENT_USER()函数，模拟用户‘Geek’。

```sql
SELECT CURRENT_USER;  
EXECUTE AS USER = 'Geek';  
SELECT CURRENT_USER;   
```

**输出:**

```sql
nidhi
Geek
```

这里，我们将用户模拟为“极客”，然后调用 CURRENT_USER 函数来获取当前用户的名称。

**示例-4 :**
使用 CURRENT_USER()函数模拟用户‘Geek’，然后再次还原代码，得到上一个当前用户。

```sql
SELECT CURRENT_USER;  
EXECUTE AS USER = 'Geek';  
SELECT CURRENT_USER;   
REVERT;
SELECT CURRENT_USER;
```

**输出:**

```sql
nidhi
Geek
nidhi
```

**应用:**

*   该函数用于在 SQL server 的数据库中查找当前用户名。