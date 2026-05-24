# MySQL |解压缩( )函数

> 原文:[https://www.geeksforgeeks.org/mysql-uncompress-function/](https://www.geeksforgeeks.org/mysql-uncompress-function/)

MySQL **解压缩()**函数用于解压缩字符串并将其恢复到原始状态。它用于已使用 COMPLATED()函数压缩的字符串。

函数的作用是:如果压缩后的字符串为空字符串，则返回空字符串。它接受一个参数，即要解压缩的压缩字符串。

**语法:**

```sql
UNCOMPRESS(string);
```

**使用的参数:**

**字符串–**用于指定要解压缩的压缩字符串。

**返回值:**
MySQL 中的解压缩()函数将压缩后的字符串解压缩后返回原始字符串。

**支持的 MySQL 版本:**

*   MySQL 5.7
*   MySQL 5.6
*   MySQL 5.5
*   MySQL 5.1
*   MySQL 5.0
*   MySQL 4.1

**示例-1:** 在字符串上实现解压缩功能。

```sql
SELECT  
UNCOMPRESS(COMPRESS('geeksforgeeks')); 
```

**输出:**

```sql
geeksforgeeks 
```

**示例-2:** 在包含字符和整数的字符串上实现解压缩功能。

```sql
SELECT 
UNCOMPRESS(COMPRESS('geeksforgeeks123')); 
```

**输出:**

```sql
geeksforgeeks123 
```

**示例-3:** 对空字符串实现 COMPRESS 函数，压缩后返回字符串长度。

```sql
SELECT  
UNCOMPRESS(COMPRESS(NULL)); 
```

**输出:**

```sql
NULL 
```