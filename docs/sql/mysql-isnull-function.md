# MySQL | ISNULL()函数

> 原文:[https://www.geeksforgeeks.org/mysql-isnull-function/](https://www.geeksforgeeks.org/mysql-isnull-function/)

MySQL **ISNULL()** 函数用于检查表达式是否为空。如果传递的表达式为空，该函数返回 1，否则返回 0。

ISNULL()函数接受表达式作为参数，并根据传递的参数返回一个值为 0 或 1 的整数。

**语法:**

```sql
ISNULL(expression)
```

**使用的参数:**

**表达式–**用于指定表达式。

**返回值:**
如果传递的表达式是 NULL 表达式，MySQL ISNULL()函数返回 1，否则返回 0。

**支持的 MySQL 版本:**

*   MySQL 5.7
*   MySQL 5.6
*   MySQL 5.5
*   MySQL 5.1
*   MySQL 5.0
*   MySQL 4.1
*   MySQL 4.0
*   MySQL 3.23

**示例-1:** 实现 ISNULL()函数。

```sql
SELECT ISNULL(NULL); 
```

**输出:**

```sql
1 
```

**示例-2:** 在字符串上实现 ISNULL()函数。

```sql
SELECT ISNULL("gfg"); 
```

**输出:**

```sql
0 
```

**示例-3:** 在整数值上实现 ISNULL()函数。

```sql
SELECT ISNULL(123); 
```

**输出:**

```sql
0 
```