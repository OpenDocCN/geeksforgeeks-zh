# MySQL 中的 UCASE()或 UPPER()函数

> 原文:[https://www . geesforgeks . org/ucase-or-upper-function-in-MySQL/](https://www.geeksforgeeks.org/ucase-or-upper-function-in-mysql/)

**1。UCASE() :**
这个函数可以用来将字符串转换成大写。该功能类似于 **UPPER()** 功能。UPPER()\UCASE()都是内置的 MySQL 函数。

**语法:**

```sql
SELECT UCASE(text)
```

**示例–**

```sql
SELECT UCASE("MySQL on geeksforgeeks is FUN!") AS UpperText;
```

**输出:**

<figure class="table">

| 【上部文字】 |
| --- |
| geeksforgeeks 上的 MySQL 很有趣！ |

</figure>

现在，这里你会看到 UPPER 函数。

**2。UPPER() :**

**语法:**

```sql
SELECT UPPER(text)
```

**示例–**

```sql
SELECT UPPER("MySQL on geeksforgeeks is FUN!") AS UpperText;
```

**输出:**

<figure class="table">

| 【上部文字】 |
| --- |
| geeksforgeeks 上的 MySQL 很有趣！ |

</figure>

**处理二进制字符串数据:**
UPPER()函数不影响二进制字符串，如 binary、VARBINARY 或 BLOB。因此，要在 UPPER()函数中使用二进制字符串，需要将字符串转换为非二进制字符串。

**示例–**

```sql
SET @str = BINARY 'Geeksforgeeks';
```

现在，如果您想读取二进制字符串，请使用下面给出的语法。

```sql
SELECT UPPER(@str), UPPER(CONVERT(@str USING utf8mb4)) AS UpperText;
```

**输出:**

<figure class="table">

| UPPER(@ str) | 上部文本 |
| --- | --- |
| 极客们 | 极客们 |

T19】</figure>

**注意–**
从输出中可以清楚地观察到，UPPER()函数对二进制字符串没有影响。