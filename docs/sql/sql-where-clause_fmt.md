# SQL WHERE 子句

> 原文: [https://www.geeksforgeeks.org/sql-where-clause/](https://www.geeksforgeeks.org/sql-where-clause/)

`WHERE` 关键字用于获取结果集中的过滤数据。

- 它用于根据特定标准获取数据。
- `WHERE` 关键字也可以通过匹配模式来过滤数据。

## 基本语法

```sql
SELECT column1, column2 FROM table_name WHERE column_name operator value;
```

- `column1`, `column2`: 表中的字段。
- `table_name`: 表名。
- `column_name`: 用于过滤数据的字段名。
- `operator`: 用于过滤的操作。
- `value`: 精确值或模式，用于在结果中获取相关数据。

## 可与 WHERE 子句一起使用的运算符列表

| **操作符** | **描述** |
| :--- | :--- |
| `>` | 大于 |
| `>=` | 大于或等于 |
| `<` | 小于 |
| `<=` | 小于或等于 |
| `=` | 等于 |
| `<>` | 不等于 |
| `BETWEEN` | 在包括范围内 |
| `LIKE` | 搜索模式 |
| `IN` | 为一列指定多个可能的值 |

[![table1](img/4fab6fceee0b1d1b256c3430eb713844.png)](https://media.geeksforgeeks.org/wp-content/cdn-uploads/table11.jpg)

## 查询示例

- 获取年龄等于 20 的学生记录。

```sql
SELECT * FROM Student WHERE Age=20;
```

输出：

| **ROLL_NO** | **NAME** | **ADDRESS** | **PHONE** | **AGE** |
| :--- | :--- | :--- | :--- | :--- |
| 3 | SUJIT | 罗塔克 | XXXXXXXXXX | 20 |
| 3 | SUJIT | 罗塔克 | XXXXXXXXXX | 20 |

- 获取 `ROLL_NO` 大于 3 的学生的姓名和地址。

```sql
SELECT ROLL_NO, NAME, ADDRESS FROM Student WHERE ROLL_NO > 3;
```

输出：

| **ROLL_NO** | **NAME** | **ADDRESS** |
| :--- | :--- | :--- |
| 4 | SURESH | 德里 |

## BETWEEN 运算符

它用于获取给定范围（包括两个值）内的过滤数据。

### 基本语法

```sql
SELECT column1, column2 FROM table_name WHERE column_name BETWEEN value1 AND value2;
```

- `BETWEEN`: 运算符名称。
- `value1` 和 `value2`: 从 `value1` 到 `value2` 的精确值，用于在结果集中获取相关数据。

### 查询示例

- 获取 `ROLL_NO` 在 1 到 3 之间（包括 1 和 3）的学生记录。

```sql
SELECT * FROM Student WHERE ROLL_NO BETWEEN 1 AND 3;
```

输出：

| **ROLL_NO** | **NAME** | **ADDRESS** | **PHONE** | **AGE** |
| :--- | :--- | :--- | :--- | :--- |
| 1 | RAM | 德里 | XXXXXXXXXX | 18 |
| 2 | RAMESH | 古尔冈 | XXXXXXXXXX | 18 |
| 3 | SUJIT | 罗塔克 | XXXXXXXXXX | 20 |
| 3 | SUJIT | 罗塔克 | XXXXXXXXXX | 20 |
| 2 | RAMESH | 古尔冈 | XXXXXXXXXX | 18 |

- 获取年龄在 20 到 30 之间（包括 20 和 30）的学生的姓名和地址。

```sql
SELECT NAME, ADDRESS FROM Student WHERE Age BETWEEN 20 AND 30;
```

输出：

| **NAME** | **ADDRESS** |
| :--- | :--- |
| SUJIT | 罗塔克 |
| SUJIT | 罗塔克 |

## LIKE 运算符

它用于通过在 `WHERE` 子句中搜索特定模式来获取过滤后的数据。

### 基本语法

```sql
SELECT column1, column2 FROM table_name WHERE column_name LIKE pattern;
```

- `LIKE`: 运算符名称。
- `pattern`: 从模式中提取精确值，用于在结果集中获取相关数据。

**注意**: 模式中的字符区分大小写。

### 查询示例

- 获取姓名以字母 'S' 开头的学生记录。

```sql
SELECT * FROM Student WHERE NAME LIKE 'S%';
```

`%`（通配符）表示后面的字符可以是任何长度和值。关于通配符的更多信息将在后面的文章中讨论。

输出：

| **ROLL_NO** | **NAME** | **ADDRESS** | **PHONE** | **AGE** |
| :--- | :--- | :--- | :--- | :--- |
| 3 | SUJIT | 罗塔克 | XXXXXXXXXX | 20 |
| 4 | SURESH | 德里 | XXXXXXXXXX | 18 |
| 3 | SUJIT | 罗塔克 | XXXXXXXXXX | 20 |

- 获取姓名中包含模式 'AM' 的学生记录。

```sql
SELECT * FROM Student WHERE NAME LIKE '%AM%';
```

输出：

| **ROLL_NO** | **NAME** | **ADDRESS** | **PHONE** | **AGE** |
| :--- | :--- | :--- | :--- | :--- |
| 1 | RAM | 德里 | XXXXXXXXXX | 18 |
| 2 | RAMESH | 古尔冈 | XXXXXXXXXX | 18 |
| 2 | RAMESH | 古尔冈 | XXXXXXXXXX | 18 |

## IN 运算符

它用于获取过滤后的数据，与由 `=` 运算符获取的数据相同，不同的是，在这里我们可以指定多个值来获取结果集。

### 基本语法

```sql
SELECT column1, column2 FROM table_name WHERE column_name IN (value1, value2, ...);
```

- `IN`: 运算符名称。
- `value1`, `value2`, ...: 与给定值匹配的精确值，用于在结果集中获取相关数据。

### 查询示例

- 获取年龄为 18 或 20 的学生的姓名和地址。

```sql
SELECT NAME, ADDRESS FROM Student WHERE Age IN (18, 20);
```

输出：

| **NAME** | **ADDRESS** |
| :--- | :--- |
| RAM | 德里 |
| RAMESH | 古尔冈 |
| SUJIT | 罗塔克 |
| SURESH | 德里 |
| SUJIT | 罗塔克 |
| RAMESH | 古尔冈 |

- 获取 `ROLL_NO` 为 1 或 4 的学生记录。

```sql
SELECT * FROM Student WHERE ROLL_NO IN (1, 4);
```

输出：

| **ROLL_NO** | **NAME** | **ADDRESS** | **PHONE** | **AGE** |
| :--- | :--- | :--- | :--- | :--- |
| 1 | RAM | 德里 | XXXXXXXXXX | 18 |
| 4 | SURESH | 德里 | XXXXXXXXXX | 18 |

本文由 [**哈什·阿加瓦尔**](https://www.facebook.com/harsh.agarwal.16752) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 `contribute@geeksforgeeks.org`。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。