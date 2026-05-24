# MySQL 中的 REVERSE()函数

> 原文:[https://www.geeksforgeeks.org/reverse-function-in-mysql/](https://www.geeksforgeeks.org/reverse-function-in-mysql/)

**REVERSE() :**
这个函数可以用来反转一个字符串并找到结果。REVERSE()函数将输入参数作为字符串，并得出该字符串的逆序。

**语法:**

```sql
SELECT REVERSE(string)

```

**注意–**
参数字符串是强制的，是要反转的字符串。

**示例-1:**

```sql
SELECT REVERSE("GFG");

```

**输出:**

| 反向(“GFG”) |
| --- |
| GFG |

**示例-2:**
使用 REVERSE()函数反转字符串:

```sql
SELECT REVERSE("Geeksforgeeks");

```

**输出:**

| 逆向(“极客”(Geeksforgeeks))； |
| --- |
| 斯基格罗夫斯基格 |

使用 REVERSE()函数反转句子:

```sql
SELECT REVERSE("Geeksforgeeks is an interesting site");

```

**输出:**

| 反向(“极客网站是一个有趣的网站”) |
| --- |
| 在你的阴道里摩擦 |

使用 REVERSE()函数查找字符串是否为回文:

```sql
DECLARE 
@input VARCHAR(100) = 'madam';
SELECT 
CASE
WHEN @input = REVERSE(@input)
THEN 'Palindrome'
ELSE 'Not Palindrome'
END result;

```

**输出:**

| 结果 |
| --- |
| 回文 |