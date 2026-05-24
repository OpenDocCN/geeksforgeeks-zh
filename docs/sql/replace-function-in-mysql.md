# MySQL 中的 REPLACE()函数

> 原文:[https://www.geeksforgeeks.org/replace-function-in-mysql/](https://www.geeksforgeeks.org/replace-function-in-mysql/)

REPLACE() [函数](https://www.geeksforgeeks.org/sql-functions-aggregate-scalar-functions/)可以用来用一个新的子字符串替换一个字符串中所有存在的子字符串。REPLACE()函数区分大小写。

**语法:**

```sql
SELECT REPLACE(string, from_string, new_string)

```

参数**字符串**用于将原字符串**从 _ 字符串**替换为新 _ 字符串。

**示例-1:**
在本例中，您将看到如何使用 replace 函数将任何字符串值替换为新的字符串值。
我们来考虑一个例子，其中“MySQL”替换为“HTML”值。下面给出的是替换函数值。

```sql
Replace "MySQL" with "HTML"

```

现在，您将看到如何读取替换值。

```sql
SELECT REPLACE("MySQL in Geeksforgeeks", "SQL", "HTML");

```

**输出:**

| REPLACE(“极客中的 MySQL”、“MySQL”、“HTML”) |
| --- |
| 极客博客中的 HTML |

**示例-2:**

```sql
Replace "X" with "A"

```

现在，如果你想读取替换值，那么使用下面给出的函数。

```sql
SELECT REPLACE("It is Good to study XXX from GFG", "X", "A");

```

**输出:**

| 替换(“学习 GFG 的某某很好”、“X”、“A”) |
| --- |
| 学习 GFG 的 AAA 很好 |

**示例-3:**

```sql
Replace "x" with "a"

```

现在，如果你想读取替换值，那么使用下面给出的函数。

```sql
SELECT REPLACE("It is Good to study xxx from GFG", "x", "a");

```

**输出:**

| 替换(“很高兴学习来自 GFG 的 xxx”，“x”，“a”) |
| --- |
| 从 GFG 学习 aaa 很好 |