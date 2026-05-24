# MySQL 中的 LCASE()或 LOWER()函数

> 原文:[https://www . geesforgeks . org/lcase-or-low-functions-in-MySQL/](https://www.geeksforgeeks.org/lcase-or-lower-functions-in-mysql/)

**1。LCASE():**
**LCASE()**函数用于将文本转换为小写。该函数类似于 LOWER()函数。

**语法:**

```sql
SELECT LCASE(text)
```

**示例:**

```sql
SELECT LCASE("Reading on GEEKSFORGEEKS is FUN") AS LowerText; 
```

**输出–**

| 下文本 |
| --- |
| 在极客博客上阅读很有趣 |

**2。LOWER() :**
**语法:**

```sql
SELECT LOWER(text)
```

**示例:**

```sql
SELECT LOWER("Studying on GeeksForGeeks is FUN") AS LowerText; 
```

**输出–**

| 下文本 |
| --- |
| 在极客网站上学习很有趣 |