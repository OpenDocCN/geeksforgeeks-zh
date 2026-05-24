# 移动台接入中的 Exp()和 Count()功能

> 原文:[https://www . geesforgeks . org/exp-and-count-function-in-ms-access/](https://www.geeksforgeeks.org/exp-and-count-function-in-ms-access/)

**1。Exp()函数:**
在 MS Access 中，Exp()函数返回 e( 2.718281)的幂次升到一个数。在这个函数中，一个数将作为一个参数传递，它将返回一个特定数的幂，e 是一个等于 2.718281 的常数。它是自然对数的基础。

**语法:**

```sql
Exp(number)

```

**示例-1 :**

```sql
SELECT Exp(6) AS ExpNum;

```

**输出–**

| 露出 |
| 403.428793492735 |

**示例-2 :**

```sql
SELECT Exp(1) AS ExpNum;

```

**输出–**

| 露出 |
| 2.71828182845905 |

**2。Count()函数:**
在 MS Access 中，Count()函数返回查询中符合条件的记录总数。当在 count 函数的帮助下执行查询表达式时，它将计算记录总数并返回该总数。

**注意–**
空值将不包括在计数中。

**语法:**

```sql
Count(expression)

```

考虑下面给出的演示数据库示例。

**表名:**斯图 _ 详情。

| 测试标识 | 用户标识 | 记号 |
| One hundred and one | GFG_1 | Sixty-seven |
| One hundred and two | GFG_2 | eighty-nine |
| One hundred and three | GFG_3 | Thirty-five |

**示例-1 :**

```sql
SELECT Count(*) AS TOTAL FROM Stu_Details;

```

**输出–**

| **总计** |
| three |

**示例-2 :**

```sql
SELECT Count(*) AS TOTAL FROM Stu_Details
Where MARKS>50;

```

**输出–**

| **总计** |
| Two |