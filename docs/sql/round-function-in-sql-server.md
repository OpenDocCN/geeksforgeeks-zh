# SQL Server 中的 ROUND()函数

> 原文:[https://www.geeksforgeeks.org/round-function-in-sql-server/](https://www.geeksforgeeks.org/round-function-in-sql-server/)

**ROUND()函数:**
这个函数在 **SQL Server** 中用来将指定的数字四舍五入到指定的小数位数。

**特征:**

*   此函数用于将指定的数字舍入到指定的小数位数。
*   该函数只接受所有类型的数字，即正、负、零。
*   这个函数接受分数。
*   此函数总是在舍入到指定的小数位后返回数字。

**语法:**

```sql
ROUND(number, decimals, operation)
```

**参数:**
该方法接受如下三个参数:

*   **数字:**指定要四舍五入的数字。
*   **小数:**指定给定数字要四舍五入到的小数位数。
*   **操作:**此为可选参数。如果它的值为 0，它会将结果舍入到小数位数。如果另一个值不是 0，它会将结果截断为小数位数。默认值为 0

**返回:**
四舍五入到指定位置后返回数字。

**示例-1 :**
获取一个四舍五入到小数点后两位的数字。

```sql
SELECT ROUND(12.3456, 2);
```

**输出:**

```sql
12.3500
```

**示例-2 :**
用操作参数 1 将数字舍入到下两个小数位，操作参数 1 表示只将指定的数字(-23.456)截断到给定的小数位，即 2。

```sql
SELECT ROUND(12.3456, 2, 1);
```

**输出:**

```sql
12.3400
```

**示例-3 :**
使用带有变量的 ROUND()函数，并将舍入后的数字设置为-2 位小数。

```sql
DECLARE @Parameter_Value FLOAT;
SET @Parameter_Value = -2;
SELECT ROUND(123.4567, @Parameter_Value);

```

**输出:**

```sql
100.0000
```

**示例-4 :**

将四舍五入到小数点后零位数。

```sql
SELECT ROUND(123.467, 0);
```

**输出:**

```sql
123.000
```

**示例-5 :**
使用带变量的 ROUND()函数，将四舍五入后的数字四舍五入到小数点后两位。

```sql
DECLARE @Number_Value FLOAT;
DECLARE @Decimals_Value INT;
SET @Number_Value = -23.456;
SET @Decimals_Value = 2;
SELECT ROUND(@Number_Value, @Decimals_Value);

```

**输出:**

```sql
-23.460000000000001
```

**示例-6 :**
用操作参数 1 将数字舍入到下两个小数位，操作参数 1 表示只将指定的数字(-23.456)截断到给定的小数位，即 2。

```sql
SELECT ROUND(-23.456, 2, 1);
```

**输出:**

```sql
-23.450
```

**应用:**
此功能用于返回四舍五入到指定位置后的数字。