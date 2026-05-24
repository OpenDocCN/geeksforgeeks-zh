# MySQL 中的 ATAN()和 ATAN2()函数

> 原文:[https://www . geesforgeks . org/atan-and-atan 2-function-in-MySQL/](https://www.geeksforgeeks.org/atan-and-atan2-function-in-mysql/)

**1。ATAN()函数:**
MySQL 中的 ATAN()函数用于返回任意数字 x 的反正切，x 的反正切定义为 x 为实数时 x 的反正切函数(x∈ℝ).

当 y 的正切等于 x 时:

```sql
tan y = x
```

那么 x 的反正切等于 x 的反正切函数，等于 y:

```sql
arctan x= tan-1 x = y
```

**语法:**

```sql
ATAN(X)

```

**参数:**该方法接受一个参数，如上所述，如下所述:

*   **X :** 一个我们要计算其反正切的数。

**返回:**返回给定数 x 的反正切。

**示例-1 :** 使用 ATAN()函数求 1 的反正切。

```sql
SELECT ATAN(1) AS Atan_Val ;

```

**输出:**

| Atan_Val |
| --- |
| 0.7853981633974483 |

**示例-2 :** 使用 ATAN()函数求 0 的反正切。

```sql
SELECT ATAN(0) AS Atan_Val ;

```

**输出:**

| Atan_Val |
| --- |
| Zero |

**示例-3 :** 使用 ATAN()函数计算(0，-1)范围内+ve 数的反正切。

```sql
SELECT ATAN(0.35) AS Atan_Val ;

```

**输出:**

| Atan_Val |
| --- |
| 0.33667481938672716 |

**示例-4 :** 使用 ATAN()函数计算一个数字的反正切。

```sql
SELECT ATAN(-2.75) AS Atan_Val ;

```

**输出:**

| Atan_Val |
| --- |
| -1.2220253232109897 |

**示例-5 :** 表中数值列的反正切值。

**表–编号:**

| X |
| --- |
| -10 |
| -1 |
| -0.50 |
| Zero |
| Zero point five |
| one |
| Fourteen |

```sql
SELECT X, ATAN(X) AS ArcTan_X  FROM Number ;

```

**输出:**

| X | arc tan _ x-弧边 _ 边 _ 边 _ 边 _ 边 _ 边 _ 边 _ 边 _ 边 _ 边 _ 边 _ 边 _ 边 _ 边 _ 边 _ 边 _ 边 _ 边 _ 边 _ 边 _ 边 _ 边 _ 边 _ 边 _ 边 |
| --- | --- |
| -10 | -1.4711276743037347 |
| -1 | -0.7853981633974483 |
| -0.50 | -0.4636476090008061 |
| Zero | Zero |
| Zero point five | 0.4636476090008061 |
| one | 0.7853981633974483 |
| Fourteen | 1.4994888620096063 |

**2。ATAN2()函数:**
MySQL 中的 ATAN2()函数用于返回指定的两个数，即 x 和 y 之间的反正切，它返回正 x 轴与原点到点(y，x)的直线之间的夹角。

**语法:**

```sql
ATAN2 (Y, X)

```

**参数:**该方法接受一个参数，如上所述，如下所述:

*   **Y，X :** 我们要计算其反正切的两个数。

**返回:**返回正 x 轴与原点到点(y，x)的直线之间的角度。

**例-1 :** 使用 ATAN2()函数求两个负数的反正切。

```sql
SELECT ATAN2(-5.44, -10.5 ) AS Atan2_Val ;

```

**输出:**

| Atan2_Val |
| --- |
| -2.6635738706445093 |

**例-2 :** 使用 ATAN2()函数求两个+ve 数的反正切。

```sql
SELECT ATAN2( 20.35, 5.60 ) AS Atan2_Val ;

```

**输出:**

| Atan2_Val |
| --- |
| 1.3022588047897063 |

**例-3 :** 表中两个数值列的反正切值。

**表–编号:**

| X | Y |
| --- | --- |
| Three point five | Two point five |
| -7.8 | five |
| Six point seven | -1.2 |
| -55.00 | -12.00 |

```sql
SELECT X, Y, ATAN2(X, Y) AS ArcTan2_XY  FROM Number ;

```

**输出:**

| X | Y | ArcTan2_XY |
| --- | --- | --- |
| Three point five | Two point five | 0.9505468408120752 |
| -7.8 | five | -1.0007558630951863 |
| Six point seven | -1.2 | -1.748021711744616 |
| -55.00 | -12.00 | -1.7856117271965553 |