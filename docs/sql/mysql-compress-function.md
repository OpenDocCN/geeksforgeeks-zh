# MySQL | COMPRESS()函数

> 原文:[https://www.geeksforgeeks.org/mysql-compress-function/](https://www.geeksforgeeks.org/mysql-compress-function/)

函数的作用是:压缩字符串。函数的返回值是一个二进制字符串。

CONSTRUCT()函数将非空字符串存储为未压缩字符串的四字节长度，然后是压缩字符串。如果字符串以空格结尾，则为“.”字符被添加到字符串中。另外，应该注意的是，空字符串存储为空字符串。函数的作用是:接受一个要压缩的字符串参数。

**语法:**

```sql
COMPRESS(string_to_compress)
```

**使用的参数:**

*   字符串到压缩–用于指定要压缩的纯文本字符串。

**返回值:**
MySQL 中的 COMPRESS 函数返回一个压缩的字符串。

**支持的 MySQL 版本:**

*   MySQL 5.7
*   MySQL 5.6
*   MySQL 5.5
*   MySQL 5.1
*   MySQL 5.0
*   MySQL 4.1

**示例-1:** 在字符串上实现压缩功能。

```sql
SELECT 
COMPRESS('geeskforgeeks'); 
```

**示例-2:** 对包含字符和整数的字符串执行压缩功能。

```sql
SELECT 
COMPRESS('geeskforgeeks123'); 
```

**输出:**

```sql
\0\0\0x?KOM-?N?/JOM?.642\06?? 
```

**示例-3:** 对字符串实现 COMPRESS 函数，压缩后返回字符串的长度。

```sql
SELECT 
COMPRESS('geeksforgeeks'), LENGTH(COMPRESS('geeksforgeeks')); 
```

**输出:**

```sql
\0\0\0x?KOM?.N?/J?\0%?f    22 
```

**示例-4:** 对空字符串实现 COMPRESS 函数，并返回压缩后的字符串长度。

```sql
SELECT 
COMPRESS(NULL), LENGTH(COMPRESS(NULL)); 
```

**输出:**

```sql
NULL NULL 
```