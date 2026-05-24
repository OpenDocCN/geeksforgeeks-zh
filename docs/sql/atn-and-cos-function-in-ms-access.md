# MS 接入中的 Atn()和 Cos()功能

> 原文:[https://www . geesforgeks . org/ATN-and-cos-function-in-ms-access/](https://www.geeksforgeeks.org/atn-and-cos-function-in-ms-access/)

**[Atn()功能](https://www.geeksforgeeks.org/sql-functions-aggregate-scalar-functions/) :**

在 MS Access 中，Atn()函数返回一个数的反正切值。它将一个数字作为参数，并返回该数字的反正切。它将有助于进行三角学的数学运算。

**语法:**

```sql
Atn(number)

```

**示例 1–**

```sql
SELECT Atn(50) AS AtnNum;

```

**输出–**

| 年 |
| 1.55079899282175 |

**示例 2–**

```sql
SELECT Atn(2) AS AtnNum;

```

**输出–**

| 年 |
| 1.10714871779409 |

**Cos()功能:**

在 MS Access 中，cos()函数返回角度的余弦值。在这个函数中，我们将传递一个角度作为参数，它将返回该角度的余弦值。这也将有助于执行三角数学运算。

**语法:**

```sql
Cos(number)

```

**示例 1–**

```sql
SELECT Cos(45) AS CosNum;

```

**输出–**

| 消费者 |
| 0.52532198881773 |

**示例 2–**

```sql
SELECT Cos(30) AS CosNum;

```

**输出–**

| 消费者 |
| 0.154251449887584 |