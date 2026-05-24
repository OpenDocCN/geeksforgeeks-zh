# MySQL 中的 PERIOD_DIFF()函数

> 原文:[https://www . geesforgeks . org/period _ diff-function-in-MySQL/](https://www.geeksforgeeks.org/period_diff-function-in-mysql/)

**PERIOD_DIFF()函数:**
这个函数在 [MySQL](https://www.geeksforgeeks.org/sql-tutorial/) 中用来返回两个指定期间的差值。这里返回的结果将以月为单位(负数或正数)，该函数中使用的两个周期参数应该采用相同的格式。

**语法:**

```sql
PERIOD_DIFF(period1, period2)

```

**参数:**
该方法接受如下两个参数。

*   **周期 1–**以 YYMM 或 YYYYMM 格式指定的第一个周期。
*   **周期 2–**以 YYMM 或 YYYYMM 格式指定的第二个周期。

**返回:**
返回两个指定周期值之差。

**例-1 :**
这里参数采用 YYMM 格式，返回的月份为负数，因为 period1 小于 period2。

```sql
SELECT PERIOD_DIFF(2003, 2011);
```

**输出:**

```sql
-8
```

**例-2 :**
这里参数采用 YYMM 格式，返回的月份为正，因为 period1 大于 period2。

```sql
SELECT PERIOD_DIFF(2020, 2007);
```

**输出:**

```sql
13
```

**例-3 :**
这里参数采用 YYYMM 格式，返回的月份为负数，因为 period1 小于 period2。

```sql
SELECT PERIOD_DIFF(202001, 202010);
```

**输出:**

```sql
-9
```

**例-4 :**
这里参数采用 YYYMM 格式，返回的月份为正，因为 period1 大于 period2。

```sql
SELECT PERIOD_DIFF(202012, 202009);
```

**输出:**

```sql
3
```

**应用:**
此功能用于返回两个指定期间的差值。