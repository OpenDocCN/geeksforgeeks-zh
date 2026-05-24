# SQL Server 中的 DEGREES()和 RADIANS()函数

> 原文:[https://www . geesforgeks . org/degrees-and-radians-in-function-SQL-server/](https://www.geeksforgeeks.org/degrees-and-radians-function-in-sql-server/)

**1。DEVELOPES()函数:**
**DEVELOPES()**函数将弧度值转换为度数。

**语法:**

```sql
DEGREES(number)
```

**参数:**必选。数值。
**数字:**是数值。
**返回:**返回一个数据类型与 numeric_expression 数据类型匹配的值。

**示例-1 :**
将弧度值转换为度数。

```sql
SELECT DEGREES(1);
```

**输出:**

```sql
57
```

**例-2 :**
当论点成立时的分数。

```sql
SELECT DEGREES(2.7);
```

**输出:**

```sql
154.698604685322294472
```

**例-3 :**
当 PI()函数是自变量时。

```sql
SELECT DEGREES(PI());
```

**输出:**

```sql
180.0
```

**例-4 :**
当传递的参数是一个表达式。

```sql
SELECT DEGREES(PI() / 4);
```

**输出:**

```sql
45.0
```

**2。弧度()函数:**
**弧度()**函数将度数转换为弧度。

**语法:**

```sql
RADIANS(number)
```

**参数:**必选。数值。
**数字:**它是一个以度为单位的数字。
**返回:**返回与 numeric_expression 相同的类型。

**示例-1 :**
将度数值转换为弧度。

```sql
SELECT RADIANS(180);
```

**输出:**

```sql
3
```

**例-2 :**
当论点成立时的分数。

```sql
SELECT RADIANS(180.0);
```

**输出:**

```sql
3.141592653589793116
```

**例-3 :**
当自变量为负值时。

```sql
SELECT RADIANS(-180);
```

**输出:**

```sql
-3
```

**例-4 :**
当传递的参数是一个表达式。

```sql
SELECT RADIANS(180 / 3);
```

**输出:**

```sql
1
```