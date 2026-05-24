# MySQL 中的 GET_FORMAT()函数

> 原文:[https://www.geeksforgeeks.org/get_format-function-in-mysql/](https://www.geeksforgeeks.org/get_format-function-in-mysql/)

**GET _ FORMAT():**
MySQL 中的这个函数有助于将日期或时间或日期时间转换为指定参数的格式化字符串。如果与 DATE_FORMAT()函数结合使用，GET_FORMAT()函数会更有用。

**语法:**

```sql
GET_FORMAT({DATE | TIME | DATETIME}, 
{'EUR' | 'USA' | 'JIS' | 'ISO' | 'INTERNAL'})
```

**参数:**

*   **日期|时间|日期时间–**日期或时间或日期时间。
*   **'欧元' | '美国' | 'JIS' | '国际标准化组织' | '内部'–**使用了不同的格式。

**返回:**
该函数将返回指定参数的格式化字符串。

**例-1:**
GET _ FORMAT()函数的基本用法。

```sql
SELECT GET_FORMAT(DATE, 'EUR') 
As New_Format;
```

**输出:**

| 新格式 |
| %d.%m.%Y ' |

**示例-2 :**
现在使用 DATE_FORMAT()函数和 GET_FORMAT()。

```sql
SELECT DATE_FORMAT('2020-12-25', GET_FORMAT(DATE, 'USA')) 
AS 'New_Format';
```

**输出:**

| 新格式 |
| 12.25.2020 |

**示例-3 :**
带有 DATE 值的 GET_FORMAT()函数的用法，这意味着第一个参数固定为 Date，第二个参数连续变化。

```sql
SELECT  
   GET_FORMAT(DATE, 'USA') AS 'USA_format',
   GET_FORMAT(DATE, 'JIS') AS 'JIS_format',
   GET_FORMAT(DATE, 'ISO') AS 'ISO_format',
   GET_FORMAT(DATE, 'EUR') AS 'EUR_format';

```

**输出:**

| 美国 _ 格式 | JIS_format | 国际标准化组织格式 | EUR_format |
| %m.%d.%Y ' | %Y-%m-%d ' | %Y-%m-%d ' | %d.%m.%Y ' |

**示例-4 :**
带有 DATETIME 值的 GET_FORMAT()函数的用法，这意味着第一个参数固定为 DateTime，第二个参数连续变化。

```sql
SELECT  
   GET_FORMAT(DATETIME, 'USA') AS 'USA_format',
   GET_FORMAT(DATETIME, 'JIS') AS 'JIS_format',
   GET_FORMAT(DATETIME, 'ISO') AS 'ISO_format',
   GET_FORMAT(DATETIME, 'EUR') AS 'EUR_format';

```

**输出:**

| 美国 _ 格式 | JIS_format | 国际标准化组织格式 | EUR_format |
| '%Y-%m-%d %H.%i.%s' | '%Y-%m-%d %H:%i:%s' | '%Y-%m-%d %H:%i:%s' | '%Y-%m-%d %H.%i.%s' |

**示例-5 :**
带有 TIME 值的 GET_FORMAT()函数的用法，这意味着第一个参数固定为 Time，第二个参数连续变化。

```sql
SELECT  
   GET_FORMAT(TIME, 'USA') AS 'USA_format',
   GET_FORMAT(TIME, 'JIS') AS 'JIS_format',
   GET_FORMAT(TIME, 'ISO') AS 'ISO_format',
   GET_FORMAT(TIME, 'EUR') AS 'EUR_format';
```

**输出:**

| 美国 _ 格式 | JIS_format | 国际标准化组织格式 | EUR_format |
| '%h:%i:%s %p' | '%H:%i:%s' | '%H:%i:%s' | '%H.%i.%s' |