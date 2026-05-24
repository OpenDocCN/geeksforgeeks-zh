# MySQL 中的 TRIM()函数

> 原文:[https://www.geeksforgeeks.org/trim-function-in-mysql/](https://www.geeksforgeeks.org/trim-function-in-mysql/)

**MySQL 中的 TRIM** ()函数用于清理数据。它还用于删除字符串中不需要的前导和尾随字符。

**语法:**

```sql
TRIM([{BOTH | LEADING | TRAILING} [remstr] FROM] str)

```

**参数:**此方法接受三参数，如上所述，如下所述:

*   **【 Both | Leading | Trailing:** The leading, trailing or both options explicitly instruct the TRIM () function to delete leading, trailing or leading and trailing unnecessary characters from the string. By default, the TRIM () function uses the both option.
*   **removed _ str:** is a string that we want to delete. If not given, spaces will be deleted.
*   **str:** It identifies the string from which we want to remove the removed_str.

**返回:**返回一个去掉了多余字符的字符串。

**示例-1 :** TRIM()函数仅删除前导空格。

```sql
SELECT TRIM(LEADING FROM "    www.geeksforgeeks.org    ") AS TrimmedString;

```

**输出:**

| 切边字符串 |
| --- |
|  |

**示例-2 :** TRIM()函数只删除尾随空格。

```sql
SELECT TRIM(TRAILING FROM "    www.geeksforgeeks.org    ") AS TrimmedString;

```

**输出:**

| 切边字符串 |
| --- |
|  |

**示例-3 :** TRIM()函数删除前导和尾随空格。

```sql
SELECT TRIM("    www.geeksforgeeks.org    ") AS TrimmedString;

```

**输出:**

| 切边字符串 |
| --- |
|  |

**示例-4 :** 带有表格数据的 TRIM()函数

**表:Student _ Details:**T16T19【罗希特T23】105T28T30

| 学生标识 | 学生名 |
| --- | --- |
| One hundred and one | 维拉特 |
| One hundred and three |
| Sika |

T0

**输出:** T12【罗希特】T14T21

| Trimming string |
| --- |
| 维拉特 |
| Sika |