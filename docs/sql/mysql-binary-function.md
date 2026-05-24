# MySQL | BINARY 函数

> 原文:[https://www.geeksforgeeks.org/mysql-binary-function/](https://www.geeksforgeeks.org/mysql-binary-function/)

MySQL **BINARY** 函数用于将一个值转换为二进制字符串。也可以使用 CAST 函数作为 CAST(值为 BINARY)来实现 BINARY 函数。
BINARY 函数接受一个参数，该参数是要转换的值，并返回一个二进制字符串。

**语法:**

```sql
BINARY value
```

**使用的参数:**

*   **值–**用于指定要转换的值。

**返回值:**
MySQL BINARY 函数在转换用户指定的值后返回一个二进制字符串。

**支持的 MySQL 版本:**

*   MySQL 5.7
*   MySQL 5.6
*   MySQL 5.5
*   MySQL 5.1
*   MySQL 5.0
*   MySQL 4.1
*   MySQL 4.0
*   MySQL 3.23

**示例-1:** 实现 BINARY 函数返回二进制字符串。

```sql
SELECT BINARY('Geeksforgeeks');  
```

**输出:**

```sql
Geeksforgeeks 
```

**示例-2:** 在不使用 BINARY 函数的情况下对两个字符串进行逐字符比较。

```sql
SELECT 'GEEKSFORGEEKS' = 'geeksforgeeks'; 
```

**输出:**

```sql
1 
```

**示例-3:** 使用 BINARY 函数逐字节比较两个字符串。

```sql
SELECT BINARY 'GEEKSFORGEEKS' = 'geeksforgeeks'; 
```

**输出:**

```sql
0 
```

**示例-4:** 使用 BINARY 函数逐字节比较两个字符串。

```sql
SELECT BINARY 'GEEKSFORGEEKS' = 'GEEKSFORGEEKS'; 
```

**输出:**

```sql
1 
```