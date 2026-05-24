# MS 接入中的 Abs()和 Avg()功能

> 原文:[https://www . geesforgeks . org/ABS-and-avg-function-in-ms-access/](https://www.geeksforgeeks.org/abs-and-avg-function-in-ms-access/)

**1。Abs()函数:**
在 MS Access 中，abs()函数返回一个正(绝对)数。在此函数中，传递正数或负数，并返回该数的绝对值。它将一个数字作为参数，并返回该数字的正值。

**语法:**

```sql
Abs(number)
```

**示例–**

```sql
SELECT Abs(-240.7) AS AbsNum;
```

**输出–**

| 阿布努姆 |
| Two hundred and forty point seven |

**示例–**

```sql
SELECT Abs(120.89) AS AbsNum;
```

**输出–**

| 阿布努姆 |
| One hundred and twenty point eight nine |

**2。Avg()函数:**
在 MS Access 中，Avg()函数用于计算数字的平均值。在这个函数中，传递一组数字/表达式，并返回输入数字的平均值。

**注意–**
如果给定了空值，那么它将被忽略。

**语法:**

```sql
Avg(expression)
```

**表–**斯图 _ 详情

| 测试 | 用户名 | 记号 |
| One hundred and one | GFG_1 | Forty-seven |
| One hundred and two | GFG_2 | seventy-eight |
| One hundred and three | GFG_3 | Sixty-seven |

**示例-1:**

```sql
SELECT Avg(MARKS) AS Average 
FROM Stu_Details;
```

**输出–**

| 平均的 |
| Sixty-four |

**示例-2:**

```sql
SELECT * 
FROM Stu_Details
WHERE MARKS > (SELECT Avg(MARKS) FROM Stu_Details);
```

**输出–**

| 测试 | 用户名 | 记号 |
| One hundred and two | GFG_2 | seventy-eight |
| One hundred and three | GFG_3 | Sixty-seven |