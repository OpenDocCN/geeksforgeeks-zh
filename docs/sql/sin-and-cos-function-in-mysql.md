# MySQL 中的 SIN()和 COS()函数

> 原文:[https://www . geesforgeks . org/sin-and-cos-function-in-MySQL/](https://www.geeksforgeeks.org/sin-and-cos-function-in-mysql/)

**1。SIN()函数:**
**SIN** ()函数在 MySQL 中用来返回任意给定数字 X 的正弦值，其中 X 以弧度给出。

**语法:**

```sql
SIN(X)
```

**参数:**必选。
**X :** 我们要计算其正弦值的数字。以弧度给出。
**返回:**返回给定数字 x 的正弦值。

**示例-1 :**
使用 SIN()函数求 0 的正弦值。

```sql
SELECT SIN(0) AS Sin_Val;
```

**输出:**

| Sin_Val |
| --- |
| Zero |

**示例-2 :**
使用 SIN()函数计算 90 度正弦，即 1.5707963267948966 弧度。

```sql
SELECT SIN(1.5707963267948966) AS Sin_Val;
```

**输出:**

| Sin_Val |
| --- |
| one |

**示例-3 :**
使用 SIN()函数计算-90 度即-1.5707963267948966 弧度的正弦。

```sql
SELECT SIN(-1.5707963267948966) AS Sin_Val;
```

**输出:**

| Sin_Val |
| --- |
| -1 |

**示例-4 :**
表中数值列的正弦值。

**表–**数字

| X |
| --- |
| -1.22 |
| -0.5 |
| Zero |
| Zero point five four |
| One point five five |

```sql
SELECT X, SIN(X) AS Sin_X  
FROM Number;
```

**输出:**

| X | Sin_X |
| --- | --- |
| -1.22 | -0.9390993563190676 |
| -0.5 | -0.479425538604203 |
| Zero | Zero |
| Zero point five four | 0.5141359916531132 |
| One point five five | 0.999783764189357 |

**2。COS()函数:**
MySQL 中的 COS()函数用于返回任意给定数字 X 的余弦值，其中 X 以弧度给出。

**语法:**

```sql
COS(X)
```

**参数:**必选。
**X :** 我们要计算其同正弦值的数字。以弧度给出。
**返回:**返回给定数字 x 的余弦值。

**示例-1 :**
使用 COS()函数求 0 的共正弦。

```sql
SELECT COS(0) AS  Cos_Val;
```

**输出:**

| Cos_Val |
| --- |
| one |

**例-2:**
90 度共正弦即 1.5707963267948966 弧度使用 COS()函数。

```sql
SELECT COS(1.5707963267948966) AS  Cos_Val;
```

**输出:**

| Cos_Val |
| --- |
| Zero |

**示例-3 :**
表中数值列的同正弦值。

**表–**数字

| X |
| --- |
| -1.22 |
| -0.5 |
| Zero |
| Zero point two five |
| One point five five |

```sql
SELECT X, COS(X) AS Cos_X  
FROM Number;
```

**输出:**

| X | Cos_X |
| --- | --- |
| -1.22 | 0.34364574631604705 |
| -0.5 | 0.8775825618903728 |
| Zero | one |
| Zero point two five | 0.9689124217106447 |
| One point five five | 0.020794827803092428 |