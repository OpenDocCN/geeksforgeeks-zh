# MySQL 中的 POW()函数

> 原文:[https://www.geeksforgeeks.org/pow-function-in-mysql/](https://www.geeksforgeeks.org/pow-function-in-mysql/)

**POW()函数:**
这个函数在 [MySQL](https://www.geeksforgeeks.org/sql-tutorial/) 中用于将指定的指数提升到指定的基数后返回一个结果。例如，如果基数为 5，指数为 2，这将返回 25 的结果。

**语法:**

```sql
SELECT POW(x, y);
```

**参数:**
该方法接受如下两个参数。

*   **x–**
    指定的基数。
*   **y–**
    指定指数。

**返回:**
将指定的指数数提升到指定的基数后返回一个结果。

**示例-1 :**
对基值 7 和指数值 2 得到 49 的结果。

```sql
SELECT POW(7, 2);
```

**输出:**

```sql
49
```

**例-2 :**
取 3 的 27 作为基数和指数值。

```sql
SELECT POW(3, 3);
```

**输出:**

```sql
27
```

**示例-3 :**
获取基值 6 和指数值 0 的结果 1。

```sql
SELECT POW(6, 0);
```

**输出:**

```sql
1
```

**示例-4 :**
获取基值 0 和指数值 4 的 0 结果。

```sql
SELECT POW(0, 4);
```

**输出:**

```sql
0
```

**应用:**
该函数用于将指定的指数提升到指定的基数后返回一个结果。