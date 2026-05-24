# MySQL | CAST()函数

> 原文:[https://www.geeksforgeeks.org/mysql-cast-function/](https://www.geeksforgeeks.org/mysql-cast-function/)

MySQL **CAST()** 函数用于将一个值从一种数据类型转换为另一种特定的数据类型。CAST()函数接受两个参数，即要转换的值和该值需要转换成的数据类型。

可以转换给定值的数据类型有:

*   日期:用于将值转换为日期数据类型。返回的格式是“年-月-日”。
*   日期时间:用于将值转换为日期时间数据类型。返回的格式是“YYYY-MM-DD HH:MM:SS”。
*   时间:用于将值转换为时间数据类型。返回的格式是“时:分:秒”。
*   它用于将一个值转换成字符数据类型。
*   有符号:用于将值转换为有符号的数据类型。
*   无符号:用于将值转换为无符号数据类型。
*   二进制:用于将值转换为二进制数据类型。

**语法:**

```sql
CAST(input_value AS datatype)
```

**使用的参数:**

*   **input _ value–**用于指定需要转换的值。
*   **数据类型–**用于指定需要转换值的数据类型。

**返回值:**
MySQL CAST()函数在转换后返回所需数据类型的值。

**支持的 MySQL 版本:**

*   MySQL 5.7
*   MySQL 5.6
*   MySQL 5.5
*   MySQL 5.1
*   MySQL 5.0
*   MySQL 4.1
*   MySQL 4.0
*   MySQL 3.23

**示例-1:** 实现 CAST()函数将值转换为 DATE 数据类型。

```sql
SELECT CAST("2019-11-21" AS DATE); 
```

**输出:**

```sql
2019-11-21 
```

**示例-2:** 实现 CAST()函数将值转换为 CHAR 数据类型。

```sql
SELECT CAST(121 AS CHAR); 
```

**输出:**

```sql
121 
```

**示例-3:** 实现 CAST()函数将值转换为 SIGNED 数据类型。

```sql
SELECT CAST(2-4 AS SIGNED); 
```

**输出:**

```sql
-2 
```

**示例-4:** 实现 CAST()函数将值转换为 UNSIGNED 数据类型。

```sql
SELECT CAST(2-4 AS UNSIGNED); 
```

**输出:**

```sql
18446744073709551614 
```