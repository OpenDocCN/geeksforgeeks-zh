# 马里亚数据库中的 SIGN()，SQRT()和 SUM()函数

> 原文:[https://www . geesforgeks . org/sign-sqrt-and-sum-function-in-Maria db/](https://www.geeksforgeeks.org/sign-sqrt-and-sum-function-in-mariadb/)

**1。符号函数:**
在[马里亚数据库](https://www.geeksforgeeks.org/difference-between-mysql-and-mariadb/)中，符号函数用于返回一个指示数字符号的值。在该函数中，将传递一个数字，如果该数字小于 0，该函数将返回 0，如果该数字等于 0，该函数将返回 1。

**语法:**

```sql
SIGN( number )
```

**示例-1:**

```sql
SELECT SIGN(509);
```

**输出:**

```sql
1
```

**示例-2:**

```sql
SELECT SIGN(0);
```

**输出:**

```sql
0
```

**例-3:**

```sql
SELECT SIGN(-346);
```

**输出:**

```sql
-1
```

**2。**
在马里亚数据库中，SQRT 函数用于返回一个数的平方根。在 SQRT 函数中，将传递一个参数值，然后该函数将返回给定输入的平方根，或者您可以说您给定的一个数字作为参数值。该数字必须为正数或 0。否则，对于负值，它将返回空值。

**语法:**

```sql
SQRT( number )
```

**示例-1:**

```sql
SELECT SQRT(121);
```

**输出:**

```sql
11
```

**示例-2:**

```sql
SELECT SQRT(0);
```

**输出:**

```sql
0
```

**例-3:**

```sql
SELECT SQRT(-64);
```

**输出:**

```sql
NULL
```

**3。求和函数:**
在马里亚数据库中，求和函数用于返回一组值的和。在这个函数中，值集作为参数传递，它将返回总和。如果条目中出现空值，则和值会忽略它们。这类似于 python 中的 sum 函数。

**语法:**

```sql
Sum(expression)
```

**样本数据库:**
**表名-IPL**

<figure class="table">T22】MIT30】RR

| 团队标识 | 团队名称 | 得分 |
| one | 码移键控 | Two hundred |
| Two | Two hundred and ten |
| three | One hundred and fifty |

</figure>

**示例-1:**

```sql
SELECT Sum(SCORE) AS Total 
From IPL;
```

**输出:**

<figure class="table">

| amount to |
| Five hundred and sixty |

</figure>

**示例-2:**

```sql
SELECT Sum(SCORE) AS Total 
From IPL
WHERE SCORE<200;
```

**输出:**

<figure class="table">

| total |
| One hundred and fifty |

</figure>

**例-3:**

```sql
SELECT Sum(SCORE) AS Total 
From IPL
WHERE SCORE>200;
```

**输出:**

<figure class="table">

| amount to |
| Two hundred and ten |

</figure>