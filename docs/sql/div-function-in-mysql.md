# MySQL 中的 DIV()函数

> 原文:[https://www.geeksforgeeks.org/div-function-in-mysql/](https://www.geeksforgeeks.org/div-function-in-mysql/)

**DIV()函数:**
这个函数在 [MySQL](https://www.geeksforgeeks.org/sql-tutorial/) 中用来在做整数除法的时候返回一个商(整数)值。例如，当 7 除以 3 时，将返回 2。

**语法:**

```sql
SELECT x DIV y;
```

**参数:**
该方法接受如下两个参数。

*   **x–**将除以 y 的指定股息
*   **y–**将除以 x 的指定除数。

**返回:**
整数除法运算完成后返回商(整数)值。

**例-1:**
7 除以 3 得到商 2。

```sql
SELECT 7 DIV 3;
```

**输出:**

```sql
2
```

**例-2:**
4 除以 4 得到商 1。

```sql
SELECT 4 DIV 4;
```

**输出:**

```sql
1
```

**例-3:**
2 除以 4 得到商 0。这里被除数小于除数，这就是为什么返回 0。

```sql
SELECT 2 DIV 4;
```

**输出:**

```sql
0
```

**应用:**
此函数用于在整数除法完成时返回商(整数)值。