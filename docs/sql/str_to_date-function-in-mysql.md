# MySQL 中的 STR_TO_DATE()函数

> 原文:[https://www . geesforgeks . org/str _ to _ date-function-in-MySQL/](https://www.geeksforgeeks.org/str_to_date-function-in-mysql/)

**STR _ TO _ DATE():**
MySQL 中的这个函数有助于将字符串值转换为日期或时间或 DateTime 值。如果将空字符串作为参数传递，该函数将返回零(0000-00-00)。

**语法:**

```sql
STR_TO_DATE(string, format)

```

**参数:**

*   **字符串–**将转换为日期时间的字符串。
*   **格式–**它将被转换的格式。

**返回:**

*   该函数将以指定的格式返回给定字符串的日期时间值。
*   如果将空字符串作为参数传递，该函数将返回零(0000-00-00)。

**示例-1 :**
使用 STR_TO_DATE()函数将' 21，7，2023 '转换为具有' %d，%m，%Y '格式的日期值。

```sql
SELECT STR_TO_DATE('21, 07, 2023', '%d, %m, %Y') 
As New_form;
```

**输出:**

| 新表单 |
| 2023-07-21 |

**示例-2 :**
使用 STR_TO_DATE()函数将“1900”转换为具有“%Y”格式的日期值。

```sql
SELECT STR_TO_DATE('1900', '%Y') 
As New_form;
```

**输出:**

| 新表单 |
| 1900-00-00 |

**示例-3 :**
使用 STR_TO_DATE()函数将' 111111 '转换为具有' %h%i%s '格式的时间值

```sql
SELECT STR_TO_DATE('111111', '%h%i%s') 
As New_form;
```

**输出:**

| 新表单 |
| 11:11:11 |

**示例-4 :**
传递一个空字符串作为 STR_TO_DATE()函数的参数。

```sql
SELECT STR_TO_DATE('', '%h') 
As New_form;
```

**输出:**

| 新表单 |
| 00:00:00 |

**示例-5 :**
使用 STR_TO_DATE()函数将' 20100212 103545 '转换为具有' %Y%m%d %h%i%s '格式的日期时间值。

```sql
SELECT STR_TO_DATE('20100212 103545', '%Y%m%d %h%i%s') 
As New_form;
```

**输出:**

| 新表单 |
| 2010-02-12 10:35:45 |