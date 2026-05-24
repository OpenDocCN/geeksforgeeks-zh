# MySQL | CONVERT()函数

> 原文:[https://www.geeksforgeeks.org/mysql-convert-function/](https://www.geeksforgeeks.org/mysql-convert-function/)

MySQL CONVERT()函数用于将一个值从一种数据类型转换为另一种数据类型。MySQL CONVERT()函数也用于将一个值从一个字符集转换为另一个字符集。它接受两个参数，即输入值和要转换的类型。

CONVERT()函数返回指定数据类型或字符集的值。

**转换数据类型的语法:**

```sql
CONVERT( input_value, data_type )
```

**转换字符集的语法:**

```sql
CONVERT( input_value USING character_set )
```

**使用的参数:**

**input _ value–**用于指定输入值。
**数据类型–**用于指定需要转换的数据类型。
**字符集–**用于指定需要转换的字符集。

**返回值:**
CONVERT()函数返回指定数据类型或字符集的值。

**支持的 MySQL 版本:**

*   MySQL 5.7
*   MySQL 5.6
*   MySQL 5.5
*   MySQL 5.1
*   MySQL 5.0
*   MySQL 4.1
*   MySQL 4.0
*   MySQL 3.23

**示例-1:** 实现 CONVERT()函数将值转换为 CHAR 数据类型。

```sql
SELECT CONVERT(198, CHAR); 
```

**输出:**

```sql
198 
```

**示例-2:** 实现 CONVERT()函数将值转换为日期时间数据类型。

```sql
SELECT CONVERT('2019-11-19', DATETIME); 
```

**输出:**

```sql
2019-11-19 00:00:00 
```

**示例-3:** 实现 CONVERT()函数将值转换为 UNSIGNED 类型。

```sql
SELECT CONVERT(2-5, UNSIGNED); 
```

**输出:**

```sql
18446744073709551613 
```

**示例-4:** 实现 CONVERT()函数，将字符串值转换为 utf8 字符集。

```sql
SELECT CONVERT('geeksforgeeks' USING utf8); 
```

**输出:**

```sql
geeksforgeeks 
```