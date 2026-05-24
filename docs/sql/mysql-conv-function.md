# MySQL | CONV()功能

> 原文:[https://www.geeksforgeeks.org/mysql-conv-function/](https://www.geeksforgeeks.org/mysql-conv-function/)

MySQL **CONV()** 函数用于将一个数字从一个基数系统转换为另一个基数系统。CONV()函数返回的值是字符串值的形式。它接受三个参数，即要转换的值、当前的数字基系统和需要将值转换为的数字基系统。

如果为新基数指定了正值，则 CONV()函数将数字视为无符号数，而如果指定了新的负基数，则 CONV()函数将数字视为有符号数。

**语法:**

```sql
CONV(number, current_base, new_base)
```

**使用的参数:**

*   **数字–**用于指定需要更改基数的数字。
*   **current _ base–**用于指定数字的当前基本系统。
*   **new _ base–**用于指定需要转换数字的期望基数系统。

**返回值:**
MySQL conv()函数在用户指定的期望基本系统中返回一个值。

**支持的 MySQL 版本:**

*   MySQL 5.7
*   MySQL 5.6
*   MySQL 5.5
*   MySQL 5.1
*   MySQL 5.0
*   MySQL 4.1
*   MySQL 4.0
*   MySQL 3.23

**示例-1:** 实现 CONV()函数，将数字从数字基数系统 10 转换为数字基数系统 2。

```sql
SELECT CONV(20, 10, 2); 
```

**输出:**

```sql
10100 
```

**示例-2:** 实现 CONV()函数，将数字从数字基数系统 2 转换为数字基数系统 10。

```sql
SELECT CONV(10100, 2, 10); 
```

**输出:**

```sql
20 
```

**示例-3:** 实现 CONV()函数，将负数从数字基数系统 8 转换为数字基数系统 10。

```sql
SELECT CONV(-6, 8, 10); 
```

**输出:**

```sql
18446744073709551610 
```

**示例-4:** 实现 CONV()函数，将数字从基数系统 16 转换为基数系统 10。

```sql
SELECT CONV('8D', 16, 10); 
```

**输出:**

```sql
141 
```