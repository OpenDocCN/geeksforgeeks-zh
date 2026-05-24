# SQL Server 中的 TAN()和 COT()函数

> 原文:[https://www . geesforgeks . org/tan-and-cot-function-in-SQL-server/](https://www.geeksforgeeks.org/tan-and-cot-function-in-sql-server/)

**1。TAN()函数:**
**TAN()**函数返回一个数的正切值。

**语法:**

```sql
TAN(number)
```

**参数:**必选。数值。
**数字:**是数值。
**返回:**返回一个数的正切的 float_expression。

**例-1 :**
当自变量为正数时。

```sql
SELECT TAN(3.25);
```

**输出:**

```sql
0.10883402551332971
```

**例 2 :**
当自变量为负数时。

```sql
SELECT TAN(-3.25);
```

**输出:**

```sql
-0.10883402551332971
```

**例-3 :**
当 PI()函数是自变量时。

```sql
SELECT TAN(PI());
         OR
DECLARE @angle FLOAT;  
SET @angle = PI();  
SELECT 'The TAN of the angle is: ' + CONVERT(VARCHAR, TAN(@angle)); 

```

**输出:**

```sql
The TAN of the angle is: -1.22465e-016
```

**例-4 :**
当论点作为一个表达式传递时。

```sql
SELECT TAN(5.2 + 1.4);
```

**输出:**

```sql
0.32785800671313348
```

**2。COT()函数:**
**COT()**函数返回一个数的余切。

**语法:**

```sql
COT(number)
```

**参数:**必选。数值。
**数字:**是数值。
**返回:**返回一个数的余切。

**例-1 :**
当自变量为正数时。

```sql
SELECT COT(4);
```

**输出:**

```sql
0.86369115445061673
```

**例-2 :**
当自变量是分数成分时。

```sql
SELECT COT(2.53);
```

**输出:**

```sql
-1.4259392442208509
```

**例-3 :**
当论证是一种表达。

```sql
SELECT COT(3 + 1);
```

**输出:**

```sql
0.86369115445061673
```

**例-4 :**
当 PI()函数是自变量时。

```sql
Select COT(PI());
         OR
DECLARE @angle FLOAT;  
SET @angle = PI();  
SELECT 'The COT of the angle is: ' + CONVERT(VARCHAR, COT(@angle));
```

**输出:**

```sql
The COT of the angle is: -8.16562e+015
```