# MySQL 中的 UNHEX()函数

> 原文:[https://www.geeksforgeeks.org/unhex-function-in-mysql/](https://www.geeksforgeeks.org/unhex-function-in-mysql/)

函数的作用是:将十六进制数转换成数字所代表的字节。它返回的值是一个二进制字符串。

**语法:**

```sql
UNHEX(str)
```

**参数:**必选。
**str :** 是要转换成数字所代表的字节的字符串。
**返回:**返回二进制字符串。如果提供了非十六进制数字，该函数返回空值。

**示例-1** :
对字符串使用 UNHEX()函数。

```sql
SELECT UNHEX('6765656B73666F726765656B73') AS String_Name;
```

**输出:**

| 字符串名称 |
| --- |
| 极客们 |

**示例-2 :**
使用 UNHEX()函数将另一个字符串。

```sql
SELECT UNHEX('48656C6C6F') AS String_Name;
```

**输出:**

| 字符串名称 |
| --- |
| 你好 |

**示例-3 :**
使用 UNHEX()函数将一个非十六进制字符串。

```sql
SELECT UNHEX('www') AS String_Name;
```

**输出:**

| 字符串名称 |
| --- |
| 空 |