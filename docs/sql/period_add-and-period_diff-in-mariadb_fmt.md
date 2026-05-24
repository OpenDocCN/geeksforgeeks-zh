# MariaDB中的PERIOD_ADD()和PERIOD_DIFF()

> 原文: [https://www.geeksforgeeks.org/period_add-and-period_diff-in-mariadb/](https://www.geeksforgeeks.org/period_add-and-period_diff-in-mariadb/)

## 1. PERIOD_ADD 功能

在MariaDB中，`PERIOD_ADD()`取一个周期（格式为YYMM或YYYYMM），并向其中添加指定的月数。在这个函数中，第一个参数是一个周期，第二个参数是一个数字。该函数将返回格式为YYYYMM的结果。

**语法:**

```sql
PERIOD_ADD( period, number)
```

**参数:**

| 参数 | 描述 |
| --- | --- |
| `period` | 一个格式化为YYMM或YYYYMM的周期。 |
| `number` | 合计要加到周期的月数。可以是负的也可以是正的。 |

**返回:**

它将返回一个周期（格式为YYMM或YYYYMM）。

**示例-1:**

```sql
SELECT PERIOD_ADD(202006, 6);
```

**输出:**

```sql
202012
```

**示例-2:**

```sql
SELECT PERIOD_ADD(201902, -10);
```

**输出:**

```sql
201804
```

**示例-3:**

```sql
SELECT PERIOD_ADD(1806, 5);
```

**输出:**

```sql
1811
```

## 2. PERIOD_DIFF 功能

在MariaDB中，`PERIOD_DIFF()`用于返回两个周期之间的月差（格式为YYMM或YYYYMM）。在这个函数中，第一个参数是周期1，第二个参数是周期2。参数`period1`和`period2`的格式必须为YYYYMM或YYMM，但格式必须相同。所以周期1可以格式化为YYYYMM，那么周期2必须格式化为YYYYMM，反之亦然。

**语法:**

```sql
PERIOD_DIFF( period1, period2 )
```

**参数:**

| 参数 | 描述 |
| --- | --- |
| `period1` | 第一个周期，将从中减去。 |
| `period2` | 第二个周期，将从周期1中减去。 |

**返回:**

返回两个周期之间的月差。

**示例-1:**

```sql
SELECT PERIOD_DIFF(202005, 202002);
```

**输出:**

```sql
3
```

**示例-2:**

```sql
SELECT PERIOD_DIFF(1908, 1901);
```

**输出:**

```sql
84
```

**示例-3:**

```sql
SELECT PERIOD_DIFF(201903, 201909);
```

**输出:**

```sql
-6
```