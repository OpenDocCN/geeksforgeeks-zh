# SQL Server 中的 FLOOR()和天花板()函数

> 原文:[https://www . geesforgeks . org/floor-and-ceiling-in-SQL-server/](https://www.geeksforgeeks.org/floor-and-ceiling-function-in-sql-server/)

**1。FLOOR()函数:**
**FLOOR()**函数返回小于或等于一个数字的最大整数值。

**语法:**

```sql
FLOOR(number)
```

**参数:**必选。数值。
**数字:**是数值。
**返回:**返回整数值。

**例-1 :**
当自变量为正数时。

```sql
SELECT FLOOR(21.53);
```

**输出:**

```sql
21
```

**例-2 :**
当自变量为负数时。

```sql
SELECT FLOOR(-21.53);
```

**输出:**

```sql
-22
```

**2。天花板()函数:**
**天花板()**函数返回大于或等于一个数字的最小整数值。

**语法:**

```sql
CEILING(number)
```

**参数:**必选。数值。
**数字:**是数值。
**返回:**返回整数值。

**例-1 :**
当自变量为正数时。

```sql
SELECT CEILING(21.53);
```

**输出:**

```sql
22
```

**例-2 :**
当自变量为负数时。

```sql
SELECT CEILING(-21.53);
```

**输出:**

```sql
-21
```