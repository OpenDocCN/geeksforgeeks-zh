# 马里亚数据库中的 POWER()，SUM()和 PI()函数

> 原文:[https://www . geesforgeks . org/power-sum-and-pi-function-in-Maria db/](https://www.geeksforgeeks.org/power-sum-and-pi-function-in-mariadb/)

**1。POWER()函数:**
在马里亚数据库中，POWER()函数用于返回 m 的 n 次方幂。在这个函数中，首先传递的两个参数是 m(数字)。它是计算中使用的基数，第二个基数是 n(数字)。它是计算中使用的指数。

**语法:**

```sql
POWER(m, n)
```

**返回:**m 的值升至 n 次方。

表--IPL

| 团队 id | 团队名称 | 得分 |
| one | 乡邮投递路线 | One hundred and forty |
| Two | 码移键控 | Two hundred and ten |
| three | 大调音阶的第三音 | One hundred and sixty |
| four | 直流电 | One hundred and seventy |

**示例-1 :**

```sql
SELECT POWER(Score) AS POWER_Score
FROM IPL
WHERE Teamname='CSK';
```

**输出:**

| 功率分数 |
| Forty-four thousand one hundred |

**示例-2 :**

```sql
SELECT (POWER(7, 2) - POWER(2, 4)) AS POWER_VALUE;
```

**输出:**

| 功率值 |
| Thirty-three |

**示例-3 :**

```sql
SELECT (POWER(10, 0) * POWER(2, 3)) AS POWER_VALUE;
```

**输出:**

| 功率值 |
| eight |

**2。SUM()函数:**
在马里亚数据库中，SUM()函数用于返回表达式的求和值。在此函数中，将传递一个或多个聚合表达式，这将返回一个结果。它的工作方式类似于已处理查询中的 sum 函数。aggregate_expression 将作为参数传递，并将返回表达式的求和值。空值被忽略。

**语法:**

```sql
SELECT SUM(aggregate_expression)
FROM tables
[WHERE conditions];
```

**返回:**表达式的求和值。

**示例-1 :**

```sql
SELECT SUM(Score) AS TOTAL_Score
FROM IPL;
```

**输出:**

| 总分 |
| Six hundred and eighty |

**示例-2 :**

```sql
SELECT (SUM(Score) + 100) AS TOTAL_Score
FROM IPL
WHERE Score<200;
```

**输出:**

| 总分 |
| Five hundred and seventy |

**示例-3 :**

```sql
SELECT (SUM(Score) * 2) AS TOTAL_Score
FROM IPL
WHERE Score>170;
```

**输出:**

| 总分 |
| Three hundred and forty |

**3。PI()函数:**
在马里亚数据库中，用于返回π (pi)值的 PI()函数最多显示 6 位小数。在这个函数中，不会传递任何参数，它将返回 pi 的值。当将双精度值用于其他双精度值的计算时，它会使用双精度值。它最多只显示 6 位小数。

**语法:**

```sql
PI( )
```

**返回:**π(π)的值，最多 6 位小数。

**示例-1 :**

```sql
SELECT PI();
```

**输出:**

```sql
3.141593
```

**示例-2 :**

```sql
SELECT PI()*3.000000000000000;
```

**输出:**

```sql
9.424777960769380
```

**示例-3 :**

```sql
SELECT PI()+5;
```

**输出:**

```sql
 8.141593
```