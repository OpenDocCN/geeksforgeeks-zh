# SQL Server 中的 NULLIF() 函数

> 原文：[https://www.geeksforgeeks.org/nullif-function-in-sql-server/](https://www.geeksforgeeks.org/nullif-function-in-sql-server/)

## 概述

SQL Server 中的 `NULLIF()` 函数用于检查两个指定的表达式是否相等。

## 特征

*   此函数用于检查两个给定的表达式是否相等。
*   如果两个给定的表达式相等，函数返回 `NULL` 值。
*   如果两个给定的表达式不相等，此函数返回第一个表达式。
*   此函数是一个高级函数。
*   此函数接受两个参数：第一个表达式和第二个表达式。

## 语法

```sql
NULLIF(expr1, expr2)
```

## 参数

此方法接受两个参数。

*   **Expression 1 和 Expression 2** – 要比较的指定表达式。

## 返回值

如果给定的两个表达式相等，则返回 `NULL`；否则，如果给定的两个表达式不相等，则返回第一个表达式。

## 示例

### 示例 1

使用 `NULLIF()` 函数并获取输出。

```sql
SELECT NULLIF(11, 11);
```

**输出：**

```sql
NULL
```

这里，因为两个表达式相等，所以返回 `NULL`。

### 示例 2

使用 `NULLIF()` 函数并获取输出。

```sql
SELECT NULLIF('ab', 'abc');
```

**输出：**

```sql
ab
```

这里，因为所述表达式不相等，所以“ab”作为输出返回。

### 示例 3

使用 `NULLIF()` 函数，并使用变量获取输出。

```sql
DECLARE @exp1 VARCHAR(50);
DECLARE @exp2 VARCHAR(50);
SET @exp1 = '2021/01/08';
SET @exp2 = '2021/01/08';
SELECT NULLIF(@exp1, @exp2);
```

**输出：**

```sql
NULL
```

### 示例 4

使用 `NULLIF()` 函数，使用 `CAST()` 函数获取输出。

```sql
SELECT NULLIF(11, CAST(11.65 AS int));
```

**输出：**

```sql
NULL
```

## 应用

这个函数用来测试两个表达式是否相等。