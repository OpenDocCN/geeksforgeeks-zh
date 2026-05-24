# SQL Server 中的 STR()函数

> 原文:[https://www.geeksforgeeks.org/str-function-in-sql-server/](https://www.geeksforgeeks.org/str-function-in-sql-server/)

**STR()** 函数将数值转换为字符值。

**语法:**

```sql
STR(float_expression [, length [, decimal]])
```

**参数:**该方法接受三个参数，如上所述，如下所述:

*   **float_expression :** 它是一个数值表达式，计算结果是一个带小数点的近似数字。
*   **长度:**是返回字符串的总长度。
*   **小数:**是小数点右边的位数。

**返回:**以字符串形式返回一个数字。

**示例-1 :**

```sql
SELECT STR(246.573, 6, 2);
```

**输出:**

```sql
246.57
```

**例-2 :**

```sql
SELECT STR(246.573, 3, 3);
```

**输出:**

```sql
246
```

**例-3 :**

```sql
SELECT STR(246.573, 2, 2);
```

**输出:**

```sql
**
```

**例-4 :**

```sql
SELECT STR(246.573, 8, 4);
```

**输出:**

```sql
246.5730
```