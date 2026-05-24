# MariaDB 中的 FLOOR()、GREATEST() 和 LEAST() 函数

> 原文: [https://www.geeksforgeeks.org/floor-greatest-and-least-function-in-mariadb/](https://www.geeksforgeeks.org/floor-greatest-and-least-function-in-mariadb/)

## 1. FLOOR() 函数
在 MariaDB 中，`FLOOR()` 函数用于返回等于或小于一个数字的最大整数值。在这个函数中，一个数字将作为参数传递，它将返回该数字的地板值。该函数的工作原理类似于 `CEIL()` 函数。

### 语法
```sql
FLOOR( number )
```

### 示例-1
```sql
SELECT FLOOR(-17.7);
```
**输出:**
```sql

```

### 示例-2
```sql
SELECT FLOOR(34.2);
```
**输出:**
```sql

```

### 示例-3
```sql
SELECT FLOOR(73);
```
**输出:**
```sql

```

## 2. GREATEST() 函数
在 MariaDB 中，`GREATEST()` 函数用于返回表达式列表中的最大值。在这个函数中，许多表达式将作为参数传递，它将返回列表中最大的值。它的工作原理类似于 Python 中的 `max()` 函数。如果表达式列表是数值，那么这个函数将返回最大的数值。如果表达式列表是字符串值，那么函数将返回最大的字符串值。如果参数中传递了 `NULL`，那么它将返回 `NULL`。

### 语法
```sql
GREATEST( expr1, expr2, ... expr_n )
```

### 示例-1
```sql
SELECT GREATEST(45, 19, 109);
```
**输出:**
```sql

```

### 示例-2
```sql
SELECT GREATEST('gfg','xyz','abc');
```
**输出:**
```sql
abc
```

### 示例-3
```sql
SELECT GREATEST('geeks', 'for',NULL,'geek');
```
**输出:**
```sql
NULL
```

## 3. LEAST() 函数
在 MariaDB 中，`LEAST()` 函数将返回表达式列表中的最小值。在这个函数中，将传递一个表达式列表，它将返回其中最小的值。它的工作原理类似于 Python 中的 `min()` 函数。如果表达式列表是数值，那么这个函数将返回最小的数值。如果表达式列表是字符串值，那么函数将返回最小的字符串值。如果在参数中传递 `NULL`，那么它将返回 `NULL`。

### 语法
```sql
LEAST( expr1, expr2, ... expr_n )
```

### 示例-1
```sql
SELECT LEAST(87, 49, 12);
```
**输出:**
```sql

```

### 示例-2
```sql
SELECT LEAST('GFG', 'ABC', 'XYZ');
```
**输出:**
```sql
ABC
```

### 示例-3
```sql
SELECT LEAST('GEEKS',NULL,'FOR');
```
**输出:**
```sql
NULL
```