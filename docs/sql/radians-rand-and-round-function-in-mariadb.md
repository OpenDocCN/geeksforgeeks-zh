# MariaDB 中的 RADIANS()，RAND()和 ROUND()函数

> 原文:[https://www . geesforgeks . org/radians-rand-and-round-function-in-mariadb/](https://www.geeksforgeeks.org/radians-rand-and-round-function-in-mariadb/)

**1。RADIANS() :**
在 MariaDB 中，RADIANS()函数用于返回一个以度为单位转换为弧度的值。在这个函数中，一个数字(以度为单位的角度)将作为参数传递。

```sql
180 degrees = π radians
```

**语法:**

```sql
RADIANS(number)
```

**返回:**角度输入的弧度值，单位为度。

**示例-1 :**

```sql
SELECT RADIANS(180);
```

**输出:**

```sql
3.141592653589793
```

**示例-2 :**

```sql
SELECT RADIANS(-14.5);
```

**输出:**

```sql
-0.2530727415391778
```

**示例-3 :**

```sql
SELECT RADIANS(30);
```

**输出:**

```sql
0.5235987755982988
```

**2。Rand() :**
在马里亚数据库中，Rand()函数用于返回一个随机数或一个范围内的随机数。在这个函数中，种子将作为参数传递。它是可选的，每次提供种子值时，它指定一个可重复的随机数序列。如果给定了一个种子值，那么这个函数将每次使用该种子值返回一个可重复的随机数序列。

**语法:**

```sql
RAND([seed])
```

**返回:**一个介于 0(包含)和 1(不包含)之间的值，如果没有给定种子，则该函数将提供一个随机数。

**示例-1 :**

```sql
SELECT RAND();
```

**输出:**

```sql
0.3456785735094069
```

**示例-2 :**

```sql
SELECT RAND(8);
```

**输出:**

```sql
0.15668530311126755
```

**示例-3 :**

```sql
SELECT RAND()*(10-1)+1;
```

**输出:**

```sql
1.564445336986748
```

**3。ROUND() :**
在 MariaDB 中，ROUND()函数用于返回四舍五入到一定小数位数的数字。在这个函数中，会传递两个参数，第一个是要取整的数字，第二个是取整到一定小数位数的数字。小数位数必须为正数或负数。

**语法:**

```sql
ROUND(number, [decimal_places])
```

**返回:**十进制输入的舍入值。

**示例-1 :**

```sql
SELECT ROUND(55.543, 1);
```

**输出:**

```sql
55.5
```

**示例-2 :**

```sql
SELECT ROUND(-89.53);
```

**输出:**

```sql
-89
```

**示例-3:**

```sql
SELECT ROUND(579.984, 0);
```

**输出:**

```sql
579
```