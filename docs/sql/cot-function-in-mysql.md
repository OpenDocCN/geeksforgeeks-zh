# MySQL 中的 COT()函数

> 原文:[https://www.geeksforgeeks.org/cot-function-in-mysql/](https://www.geeksforgeeks.org/cot-function-in-mysql/)

**COT()函数:**
这个函数在 [MySQL](https://www.geeksforgeeks.org/sql-tutorial/) 中用来返回指定数的余切。如果指定的数字为 0，将返回错误或空值。在直角三角形中，一个角的余切是它相邻边的长度除以相对边的长度。同样，这也可以定义为 x 的余切是 x 的余弦除以 x 的正弦，其中 x 是角度。

**语法:**

```sql
COT(number)
```

**参数:**
该方法接受如下参数。

*   **数字–**指定的数值。

**返回:**
返回指定数的余切。

**例-1:**
1 的余切为 0.642926434606

```sql
SELECT COT(1);
```

**输出:**

```sql
0.6420926159343306
```

**示例-2:**
0 的余切返回一个错误。

```sql
SELECT COT(0);
```

**输出:**

```sql
Error in SQL:
DOUBLE value is out of range in 'cot(0)'
```

**例-3 :**
例-3 的余切为 0.649269343606

```sql
SELECT COT(-3);
```

**输出:**

```sql
7.015252551434534
```

**例-4:**
3 的余切是-7.015255514345

```sql
SELECT COT(3);
```

**输出:**

```sql
-7.015252551434534
```

**应用:**
这个函数用来返回指定数的余切。