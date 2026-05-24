# 匹配字符串任意部分的 SQL 查询

> 原文:[https://www . geesforgeks . org/SQL-查询匹配字符串的任何部分/](https://www.geeksforgeeks.org/sql-query-to-match-any-part-of-string/)

**SQL 模式匹配:**

它用于搜索字符串或子字符串，以便从字符串中找到某个字符或某组字符。我们可以使用 SQL 的 [LIKE 运算符](https://www.geeksforgeeks.org/sql-like/)来搜索子字符串。LIKE 运算符与 [WHERE 子句](https://www.geeksforgeeks.org/sql-where-clause/)一起使用，在一串列中搜索模式。LIKE 运算符与两个通配符结合使用。

1.  **Percent sign (%)** **:** indicates zero, one or more variable-length characters.
2.  **Underline (_):** indicates a single character with a fixed length.

**示例:**

在这个例子中，我们将为我们的数据库创建一个模式，并将其命名为 geeksforgeeks。之后，我们将在其中创建一个名为 geeks_data 的表，并尝试从表的数据中搜索一个子字符串。

**步骤 1:创建数据库:**

为了创建数据库，我们需要使用 create 操作符。

```sql
CREATE DATABASE geeksforgeeks;
```

**步骤 2:在数据库内部创建一个表:**

在这一步中，我们将在 geeksforgeeks 数据库中创建表 geeks_data。

```sql
CREATE TABLE geeksforgeeks.geeks_data(id INT, 
                                    first_name VARCHAR(255),
                                    last_name VARCHAR(255),
                                    text_description  VARCHAR(255),
                                    PRIMARY KEY(id));
```

**第三步:将数据插入表中:**

为了在数据库中插入数据，我们需要使用 insert 操作符。

```sql
INSERT INTO geeksforgeeks.geeks_data (id, first_name, last_name, text_description) 
VALUES (1, "Rahul", "Khanna", "I am a backend developer who also like to technical content writing");
```

<figure class="table">

| 身份证明（identification） | 名字 | 姓氏 | 文本描述 |
| one | Rahul | 汗纳 | I am a back-end developer, and I also like to write with technical content. |

</figure>

**第四步:使用相似运算符搜索模式:**

```sql
SELECT first_name FROM geeksforgeeks.geeks_data WHERE text_description LIKE '%backend%developer%';
```

**第五步:输出:**

我们将获得描述中**后端开发人员**所在的**名字**。

<figure class="table">

| Name _ name |
| Huer |

</figure>