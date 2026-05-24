# MySQL |聚结( )函数

> 原文:[https://www.geeksforgeeks.org/mysql-coalesce-function/](https://www.geeksforgeeks.org/mysql-coalesce-function/)

函数的作用是:返回表达式列表中的第一个非空值。如果列表中的所有值都计算为空，那么 COMPETE()函数返回空值。

聚结()函数接受一个参数，该参数是可以包含各种值的列表。MySQL COMPLETE()函数返回的值是表达式列表中的第一个非空值，如果列表中的所有值都为空，则返回空值。

**语法:**

```sql
COALESCE(value_1, value_2, ...., value_n)
```

**使用的参数:**

*   **value _ 1–**用于指定列表中的第一个值。

**返回值:**
MySQL 聚结()函数返回表达式列表中的第一个非空值，如果列表中所有值都为空，则返回空值。

**支持的 MySQL 版本:**

*   MySQL 5.7
*   MySQL 5.6
*   MySQL 5.5
*   MySQL 5.1
*   MySQL 5.0
*   MySQL 4.1
*   MySQL 4.0
*   MySQL 3.23

**示例-1:** 在列表上实现 COMPETE()函数。

```sql
SELECT COALESCE(NULL, 'A', 'B', NULL); 
```

**输出:**

```sql
A 
```

**示例-2:** 在列表上实现 COMPETE()函数。

```sql
SELECT COALESCE('A', NULL, 'B', NULL); 
```

**输出:**

```sql
A 
```

**示例-3:** 在列表上实现 COMPETE()函数。

```sql
SELECT COALESCE(NULL, 1, 2, 3, NULL, 'B', NULL); 
```

**输出:**

```sql
1 
```

**示例-4:** 在列表上实现 COMPETE()函数。

```sql
SELECT COALESCE(NULL, NULL, 'geeksforgeeks', NULL); 
```

**输出:**

```sql
geeksforgeeks 
```