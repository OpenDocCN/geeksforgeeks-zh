# SQL Server 中的 SIN()和 COS()函数

> 原文:[https://www . geesforgeks . org/sin-and-cos-function-in-SQL-server/](https://www.geeksforgeeks.org/sin-and-cos-function-in-sql-server/)

**1。函数:**
**函数返回一个数字的正弦值。**

**语法:**

```sql
SIN(number)
```

**参数:**必选。数值。
**数字:**是数值。
**返回:**返回一个数的正弦的 float_expression。

**例-1 :**
当自变量为正数时。

```sql
SELECT SIN(5);
```

**输出:**

```sql
-0.95892427466313845
```

**例-2 :**
当自变量为负数时。

```sql
SELECT SIN(-5);
```

**输出:**

```sql
0.95892427466313845
```

**例-3 :**
当 PI()函数是自变量时。

```sql
SELECT SIN(PI());
```

**输出:**

```sql
1.2246467991473532E-16
```

**例-4 :**
当传递的参数是一个表达式。

```sql
SELECT SIN(4 * 3);
```

**输出:**

```sql
-0.53657291800043494
```

**2。COS()函数**
**COS()**函数返回一个数的余弦值。

**语法:**

```sql
COS(number)
```

**参数:**必选。数值。
**数字:**是数值。
**返回:**返回一个数的余弦值。

**例-1 :**
当自变量为正数时。

```sql
SELECT COS(4);
```

**输出:**

```sql
-0.65364362086361194
```

**例-2 :**
当自变量是分数成分时。

```sql
SELECT COS(2.53);
```

**输出:**

```sql
-0.81873459927738157
```

**例-3 :**
当 PI()函数是自变量时。

```sql
SELECT COS(PI());
```

**输出:**

```sql
-1
```