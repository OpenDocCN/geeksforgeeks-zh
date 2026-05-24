# MySQL 中的 CHAR_LENGTH()函数

> 原文:[https://www . geesforgeks . org/char _ length-function-in-MySQL/](https://www.geeksforgeeks.org/char_length-function-in-mysql/)

**MySQL 中的 CHAR_LENGTH** ()函数用于查找给定字符串的长度(以字符为单位)。它计算字符数，忽略字符是单字节还是多字节。

**语法:**

```sql
CHAR_LENGTH(str)

```

**参数:**该方法接受一个参数，如上所述，如下所述:

*   **String:** A string whose length needs to be calculated.

**返回:**返回给定字符串的长度。

**示例-1 :** CHAR_LENGTH()函数，用于查找字符串的长度。

```sql
SELECT CHAR_LENGTH("geeksforgeeks") AS LengthOfString

```

**输出:**

| Length |
| --- |
| 13 |

**示例-2 :** CHAR_LENGTH()函数，用于查找字符串的长度。

```sql
SELECT CHAR_LENGTH("SQL Tutorial in geeksforgeeks") AS LengthOfString

```

**输出:**

| Length |
| --- |
| 29 |

**示例-3 :** CHAR_LENGTH()函数，用于查找表的一列中每个字符串的长度。

**表–学生 _ 详情:** T21】2T29】3

| Student voucher | Student _ name | Total _ achievement |
| --- | --- | --- |
| one | Amit | Four hundred and fifty |
| Alnwick | Four hundred and seventy |
| three |

**输出:** T12】6T15T19T23T26

| Length name |
| --- |
| four |
| seven | six |