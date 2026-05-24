# SQL | 通配符运算符

> 原文: [https://www.geeksforgeeks.org/sql-wildcard-operators/](https://www.geeksforgeeks.org/sql-wildcard-operators/)

先决条件: [SQL | WHERE 子句](https://www.geeksforgeeks.org/sql-where-clause/)
在上面提到的文章中，讨论了 `WHERE` 子句，其中也解释了 `LIKE` 运算符，现在让我们更深入地了解通配符一词。

通配符运算符与 `LIKE` 运算符一起使用，有四种基本运算符:

| **操作员** | **描述** |
| --- | --- |
| `%` | 它用于替代零个或多个字符。 |
| `_` | 它用于替代一个字符。 |
| `_` | 它用于替换一系列字符。 |
| `[字符范围]` | 它用于获取括号内指定的匹配字符集或字符范围。 |
| `[^range_of_characters]` 或 `[!字符范围]` | 它用于获取括号内指定的不匹配的字符集或字符范围。 |

**基本语法:**

```sql
SELECT column1,column2 FROM table_name WHERE column LIKE wildcard_operator;
column1 , column2: fields in the table
table_name: name of table
column: name of field used for filtering data
```

[![table1](img/4fab6fceee0b1d1b256c3430eb713844.png)](https://media.geeksforgeeks.org/wp-content/cdn-uploads/table11.jpg)

**查询**

*   从 `Student` 表中获取 `NAME` 以字母 ‘T’ 结尾的记录。

```sql
SELECT * FROM Student WHERE NAME LIKE '%T';
```

输出:

| **滚动 _ 否** | **名称** | **地址** | **PHONE** | **年龄** |
| --- | --- | --- | --- | --- |
| three | SUJIT | 罗塔克 | XXXXXXXXXX | Twenty |
| three | SUJIT | 罗塔克 | XXXXXXXXXX | Twenty |

*   从 `Student` 表中获取 `NAME` 以 ‘RAMES’ 开头，后跟任意一个字符的记录。

```sql
SELECT * FROM Student WHERE NAME LIKE 'RAMES_';
```

输出:

| **滚动 _ 否** | **名称** | **地址** | **PHONE** | **年龄** |
| --- | --- | --- | --- | --- |
| Two | RAMESH | 古尔冈 | XXXXXXXXXX | Eighteen |

*   从 `Student` 表中获取 `ADDRESS` 包含字母 ‘a’, ‘b’, 或 ‘c’ 的记录。

```sql
SELECT * FROM Student WHERE ADDRESS LIKE '%[A-C]%';
```

输出:

| **滚动 _ 否** | **名称** | **地址** | **PHONE** | **年龄** |
| --- | --- | --- | --- | --- |
| Two | RAMESH | 古尔冈 | XXXXXXXXXX | Eighteen |
| Two | RAMESH | 古尔冈 | XXXXXXXXXX | Eighteen |
| three | SUJIT | 罗塔克 | XXXXXXXXXX | Twenty |
| three | SUJIT | 罗塔克 | XXXXXXXXXX | Twenty |

*   从 `Student` 表中获取 `ADDRESS` 不包含字母 ‘a’, ‘b’, 或 ‘c’ 的记录。

```sql
SELECT * FROM Student WHERE ADDRESS LIKE '%[^A-C]%';
```

输出:

| **滚动 _ 否** | **名称** | **地址** | **PHONE** | **年龄** |
| --- | --- | --- | --- | --- |
| one | 随机存取存储器(random access memory 的缩写)ˌ随机访问内存(random-access memory 的缩写) | 德里 | XXXXXXXXXX | Eighteen |
| four | SURESH | 德里 | XXXXXXXXXX | Eighteen |

*   从 `Student` 表中获取 `PHONE` 字段在第1位是 ‘9’ 且在第4位是 ‘5’ 的记录。

```sql
SELECT * FROM Student WHERE PHONE LIKE '9__5%';
```

输出:

| **滚动 _ 否** | **名称** | **地址** | **PHONE** | **年龄** |
| --- | --- | --- | --- | --- |
| one | 随机存取存储器(random access memory 的缩写)ˌ随机访问内存(random-access memory 的缩写) | 德里 | XXXXXXXXXX | Eighteen |

*   从 `Student` 表中获取 `ADDRESS` 总共包含6个字符的记录。

```sql
SELECT * FROM Student WHERE ADDRESS LIKE '______';
```

输出:

| **滚动 _ 否** | **名称** | **地址** | **PHONE** | **年龄** |
| --- | --- | --- | --- | --- |
| three | SUJIT | 罗塔克 | XXXXXXXXXX | Twenty |
| three | SUJIT | 罗塔克 | XXXXXXXXXX | Twenty |

*   从 `Student` 表中获取 `ADDRESS` 在任意位置包含 ‘OH’ 的记录，并且结果集不应包含重复数据。

```sql
SELECT DISTINCT * FROM Student WHERE ADDRESS LIKE '%OH%';
```

输出:

| **滚动 _ 否** | **名称** | **地址** | **PHONE** | **年龄** |
| --- | --- | --- | --- | --- |
| three | SUJIT | 罗塔克 | XXXXXXXXXX | Twenty |

本文由 **[Pratik Agarwal](https://www.facebook.com/Pratik.Agarwal01)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 `contribute@geeksforgeeks.org`。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。