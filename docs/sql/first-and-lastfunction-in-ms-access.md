# MS 接入中的第一个()和最后一个()功能

> 原文:[https://www . geesforgeks . org/first-and-last function-in-ms-access/](https://www.geeksforgeeks.org/first-and-lastfunction-in-ms-access/)

**1。First()函数:**
在 MS Access 中，First()函数用于从查询返回的结果集中的第一条记录返回字段值。

**语法:**

```sql
First(expr)

```

**参数:**

*   **expr :** 它表示一个字符串表达式，标识包含我们要使用的数据的字段，或者表示使用该字段中的数据执行计算的表达式。

**返回:**返回结果集中的第一条记录。

<center>
**Table –** Employee_Details

| **Emp** _id | Emp_Name | 经验 |
| --- | --- | --- |
| One hundred and one | Amit | five |
| One hundred and two | Rahul | Ten |
| One hundred and three | 苏哈尼 | eight |

</center>

**示例-1 :**

```sql
SELECT First(Emp_id) AS EmployeeId FROM Employee_Details;

```

**输出:**

| 员工 Id |
| --- |
| One hundred and one |

**示例-2 :**

```sql
SELECT First(Emp_Name) AS FirstEmployee FROM Employee_Details;

```

**输出:**

| 第一个员工 |
| --- |
| Amit |

**2。Last()函数:**
在 MS Access 中，Last()函数用于返回查询返回的结果集中最后一条记录的字段值。

**语法:**

```sql
Last(expr)

```

**参数:**

*   **expr :** 它表示一个字符串表达式，标识包含我们要使用的数据的字段，或者表示使用该字段中的数据执行计算的表达式。

**返回:**返回结果集中的最后一条记录。

**示例-2 :**

```sql
SELECT Last(Emp_id) AS EmployeeId FROM Employee_Details;

```

**输出:**

| 员工 Id |
| --- |
| One hundred and three |

**示例-2 :**

```sql
SELECT Last(Emp_Name) AS LastEmployee FROM Employee_Details;

```

**输出:**

| lastamployee |
| --- |
| 苏哈尼 |