# MySQL 正则表达式（REGEXP）

> 原文：[https://www.geeksforgeeks.org/mysql-regular-expressions-regexp/](https://www.geeksforgeeks.org/mysql-regular-expressions-regexp/)

MySQL 支持另一种基于正则表达式和 `REGEXP` 运算符的模式匹配操作。

1.  它提供了强大而灵活的模式匹配，可以帮助我们为数据库系统实现强大的搜索工具。
2.  `REGEXP` 是执行正则表达式模式匹配时使用的运算符。`RLIKE` 是同义词。
3.  它还支持许多元字符，这些元字符在执行模式匹配时允许更大的灵活性和控制。
4.  反斜杠用作转义字符。只有在使用了双反斜杠的情况下，才会在模式匹配中考虑它。
5.  不区分大小写。

| **图案** | **模式匹配什么** |
| :--- | :--- |
| `*` | 它前面零个或多个字符串实例 |
| `+` | 它前面的一个或多个字符串实例 |
| `.` | 任何单个字符 |
| `?` | 匹配前面字符串的零个或一个实例。 |
| `^` | `caret(^)`匹配字符串的开头 |
| `$` | 字符串结尾 |
| `[abc]` | 方括号中列出的任何字符 |
| `[^abc]` | 方括号中未列出的任何字符 |
| `[A-Z]` | 匹配任何大写字母。 |
| `[a-z]` | 匹配任何小写字母 |
| `[0-9]` | 匹配从 0 到 9 的任何数字。 |
| `[[:<:]]` | 匹配单词的开头。 |
| `[[:>:]]` | 匹配单词的结尾。 |
| `[:class:]` | 匹配字符类，即`[:alpha:]`匹配字母，`[:space:]`匹配空格，`[:punct:]`是匹配标点符号，而`[:upper:]`是匹配大写字母。 |
| `p1|p2|p3` | 交替；匹配任何模式 `p1`、`p2` 或 `p3` |
| `{n}` | 前面元素的 n 个实例 |
| `{m，n}` | 前面元素的 m 到 n 个实例 |

**举例说明：**

*   匹配字符串开头（`^`）：
    给出所有以‘sa’开头的名字。例如 - sam, samarth。

```sql
SELECT name FROM student_tbl WHERE name REGEXP '^sa';
```

*   匹配字符串结尾（`$`）：
    给出所有以‘on’结尾的名字。例如 – norton, merton。

```sql
SELECT name FROM student_tbl WHERE name REGEXP 'on$';
```

*   匹配前面字符串的零个或一个实例（`?`）：
    给出所有包含‘com’的标题。例如 – comedy, romantic comedy。

```sql
SELECT title FROM movies_tbl WHERE title REGEXP 'com?';
```

*   匹配模式 `p1`、`p2` 或 `p3` 中的任何一个（`p1|p2|p3`）：
    给出所有包含‘be’或‘ae’的名字。例如 – Abel, Baer。

```sql
SELECT name FROM student_tbl WHERE name REGEXP 'be|ae';
```

*   匹配方括号中列出的任何字符（`[abc]`）：
    给出所有包含‘j’或‘z’的名字。例如 – Lorentz, Rajs。

```sql
SELECT name FROM student_tbl WHERE name REGEXP '[jz]';
```

*   匹配‘a’到‘z’之间任何小写字母（`[a-z]`）以及任何单个字符（`.`）：
    检索所有名字，这些名字包含一个在‘b’和‘g’范围内的字母，后跟任何字符，再后跟字母‘a’。例如 – Tobias, sewall。

```sql
SELECT name FROM student_tbl WHERE name REGEXP '[b-g].[a]';
```

*   匹配方括号中未列出的任何字符（`[^abc]`）：
    给出所有不包含‘j’或‘z’的名字。例如 – nerton, sewall。

```sql
SELECT name FROM student_tbl WHERE name REGEXP '[^jz]';
```

*   匹配单词结尾（`[[:>:]]`）：
    给出所有以字符“ack”结尾的标题。例如 – Black。

```sql
SELECT title FROM movies_tbl WHERE title REGEXP 'ack[[:>:]]';
```

*   匹配单词开头（`[[:<:]]`）：
    给出所有以字符“for”开头的标题。例如 – Forgetting Sarah Marshal。

```sql
SELECT title FROM movies_tbl WHERE title REGEXP '[[:<:]]for';
```

*   匹配字符类（`[:class:]`）：
    即`[:lower:]`-小写字符、`[:digit:]`-数字字符等。
    给出所有仅包含字母字符的标题。例如 – strange things, avengers。

```sql
SELECT title FROM movies_tbl WHERE title REGEXP '[:alpha:]';
```