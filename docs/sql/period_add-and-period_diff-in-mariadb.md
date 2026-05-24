# 马里亚数据库

中的 PERIOD_ADD()和 PERIOD_DIFF()

> 原文:[https://www . geesforgeks . org/period _ add-and-period _ diff-in-Maria db/](https://www.geeksforgeeks.org/period_add-and-period_diff-in-mariadb/)

**1。PERIOD_ADD 功能:**

在马里亚数据库中，PERIOD_ADD()取一个句点(格式为 YYMM 或 YYYMM)，并向其中添加指定的月数。在这个函数中，第一个参数是一个周期，第二个参数是一个数字。该函数将返回格式为 YYYYMM 的结果。

**语法:**

```sql
PERIOD_ADD( period, number)

```

**参数:**

| 参数 | 描述 |
| --- | --- |
| 时期 | 一个格式化为 YYMM 或 YYMM 的时期。 |
| 号 | 合计要加到期间的月数。可以是负的也可以是正的 |

**返回:**

它将返回一个句点(格式为 YYMM 或 YYYYMM)。

**示例-1 :**

```sql
SELECT PERIOD_ADD(202006, 6);

```

**输出:**

```sql
202012

```

**示例-2 :**

```sql
SELECT PERIOD_ADD(201902, -10);

```

**输出:**

```sql
201804

```

**示例-3 :**

```sql
SELECT PERIOD_ADD(1806, 5);

```

**输出:**

```sql
201811

```

**2。PERIOD_DIFF 功能:**

在马里亚数据库中，PERIOD_DIFF()用于返回两个期间之间的月差(格式为 YYMM 或 YYYYMM)。在这个函数中，第一个参数是周期 1，第二个参数是周期 2。参数 period1 和 period2 的格式必须为 YYYYMM 或 YYYMM，但格式必须相同。所以周期 1 可以格式化为 YYYYMM，那么周期 2 必须格式化为 YYYMM，反之亦然。

**语法:**

```sql
PERIOD_DIFF( period1, period2 )

```

**参数:**

| **parameter** | **Description** |
| --- | --- |
| Cycle 1 | The first cycle in February will be subtracted. |
| Cycle 2 | The second cycle will be subtracted from cycle 1\. |

**返回:**

返回两个期间之间的月差

**示例-1 :**

```sql
SELECT PERIOD_DIFF(202005, 202002);

```

**输出:**

```sql
3

```

**示例-2 :**

```sql
SELECT PERIOD_DIFF(1908, 1901);

```

**输出:**

```sql
7

```

**示例-3 :**

```sql
SELECT PERIOD_DIFF(201903, 201909);

```

**输出:**

```sql
6

```