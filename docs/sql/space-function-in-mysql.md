# MySQL 中的 SPACE()函数

> 原文:[https://www.geeksforgeeks.org/space-function-in-mysql/](https://www.geeksforgeeks.org/space-function-in-mysql/)

**MySQL 中的 SPACE** ()函数用于返回由指定的空格字符组成的字符串。

**语法:**

```sql
SPACE(num)

```

**参数:**该方法接受一个参数，如上所述，如下所述:

*   **num:** It is an integer that indicates how many spaces it contains.

**返回:**返回包含指定数量空格的字符串。

**示例-1 :** SPACE()函数返回只包含空格的字符串。

```sql
SELECT SPACE(6) AS String_Name;

```

**输出:**

| 弦 _ 名 |
| --- |
|  |

**示例-2 :** 将 SPACE()函数与 CONCAT()函数一起应用将返回一个字符串。

```sql
SELECT CONCAT('Geeks', SPACE(3), 'For', SPACE(3), 'Geeks') AS Company_Name;

```

**输出:**

| Company _ name |
| --- |
| Geek is Geek |

**示例-3 :** 在表格中使用 SPACE()函数。

**表:Player _ Details:**T15】ViratT17】科勒 T19T21】102T23】罗希特 T25 夏尔马T28

| 玩家标识 | 名字 | 姓氏 |
| --- | --- | --- |
| One hundred and one |
| One hundred and three |

**输出:**

| [Full name] |
| --- |
| 【翻白菜】 |
| 【原始【夏尔马】 |