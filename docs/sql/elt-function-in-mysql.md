# MySQL 中的 ELT()函数

> 原文:[https://www.geeksforgeeks.org/elt-function-in-mysql/](https://www.geeksforgeeks.org/elt-function-in-mysql/)

在本文中，我们将通过例子来介绍英语教学功能。在 ELT 函数中，数字字段将说明有多少个字符串。

MySQL 中的 ELT [函数用于返回参数列表中指定的索引号处的字符串。在这个函数中有数字字段和字符串字段。
**语法:**](https://www.geeksforgeeks.org/sql-functions-aggregate-scalar-functions/)

```sql
 ELT(N, string1, string2, string3, string4, …)

```

**参数:**
该方法接受两个参数，如上所述，如下所述。

*   **N :** 是整数，是要检索的字符串的索引。
*   **string1、string2、string3 :** 我们要从中检索的字符串列表。

**返回–**
返回指定索引处的字符串。如果在指定的索引处没有字符串，它将返回空值

**示例-1 :**
使用 ELT()函数检索字符串。

```sql
Select ELT(4, 'Learning', 'SQL', 'at', 'geeksforgeeks', 'is', 'fun') 
As Res_Str;

```

**输出:**

| 坚持住 |
| --- |
| 极客们 |

**示例-2 :**
使用 ELT()函数检索字符串。

```sql
Select ELT(1, 'Learning', 'SQL', 'at', 'geeksforgeeks', 'is', 'fun') 
As Res_Str;

```

**输出:**

| 坚持住 |
| --- |
| 学问 |

**示例-3 :**
当指定索引处没有字符串时，使用 ELT()函数检索字符串。

```sql
Select ELT(8, 'Learning', 'SQL', 'at', 'geeksforgeeks', 'is', 'fun') 
As Res_Str;

```

**输出:**

| 坚持住 |
| --- |
| 空 |