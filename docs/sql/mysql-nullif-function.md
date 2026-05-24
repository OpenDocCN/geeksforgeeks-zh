# MySQL | NULLIF()函数

> 原文:[https://www.geeksforgeeks.org/mysql-nullif-function/](https://www.geeksforgeeks.org/mysql-nullif-function/)

MySQL **NULLIF()** 函数用于两个表达式的比较。函数的作用是:如果两个表达式相等，返回空值，否则返回第一个表达式。函数的作用是:接受表达式作为参数，如果两者相等，则返回空值。

**语法:**

```sql
NULLIF(expression1, expression2)
```

**使用的参数:**

**表达式 1–**用于指定第一个表达式。
**表达式 2–**用于指定第二个表达式。

**返回值:**
如果传递的两个表达式相等，MySQL NULLIF()函数返回空值，否则如果两个表达式不相等，则返回第一个表达式。

**支持的 MySQL 版本:**

*   MySQL 5.7
*   MySQL 5.6
*   MySQL 5.5
*   MySQL 5.1
*   MySQL 5.0
*   MySQL 4.1
*   MySQL 4.0
*   MySQL 3.23

**示例-1:** 通过比较两个相同的字符串来实现 NULLIF()函数。

```sql
SELECT NULLIF("Geeksforgeeks", "Geeksforgeeks"); 
```

**输出:**

```sql
NULL 
```

**示例-2:** 通过比较两个不相等的字符串来实现 NULLIF()函数。

```sql
SELECT NULLIF("123", "Geeksforgeeks"); 
```

**输出:**

```sql
123 
```

**示例-3:** 通过比较两个整数值实现 NULLIF()函数。

```sql
SELECT NULLIF(2, 4); 
```

**输出:**

```sql
2 
```