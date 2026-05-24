# SQL 中内部连接和外部连接的区别

> 原文:[https://www . geeksforgeeks . org/SQL 内部联接和外部联接的区别/](https://www.geeksforgeeks.org/difference-between-inner-join-and-outer-join-in-sql/)

**1。内部连接:**
是 SQL 中[连接](https://www.geeksforgeeks.org/sql-join-set-1-inner-left-right-and-full-joins/)操作的一种。内部联接是一种返回两个或多个表之间的组合元组的操作，其中至少有一个属性是公共的。如果表之间没有共同的属性，那么它将不返回任何内容。

语法:

```sql
select * 
from table1 INNER JOIN table2
on table1.column_name = table2.column_name;
```

运筹学

```sql
select *
from table1 JOIN table2
on table1.column_name = table2.column_name;
```

**2。**外连接:
这是一种 SQL 中的连接操作。外部联接是一种从指定表中返回组合元组的操作，即使联接条件会失败。在 SQL 中有三种类型的外部连接，即

1.  左外连接
2.  右外连接
3.  完全外部连接

左外连接的语法:

```sql
select *
from table1 LEFT OUTER JOIN table2
on table1.column_name = table2.column_name;
```

右外连接的语法:

```sql
select *
from table1 RIGHT OUTER JOIN table2
on table1.column_name = table2.column_name;
```

完全外部联接的语法:

```sql
select *
from table1 FULL OUTER JOIN table2
on table1.column_name = table2.column_name;
```

以下是**内部连接**和**外部连接**之间的差异表:

<center>

| S.No | 内部连接 | 外部连接 |
| 1. | 它返回两个或多个表之间的组合元组。 | 它从指定的表中返回组合元组，即使连接条件会失败。 |
| 2. | Used 子句 INNER JOIN 和 JOIN。 | 左外连接、右外连接、全外连接等。 |
| 3. | 当任何属性不常见时，它将不返回任何内容。 | 它不依赖于公共属性。如果属性为空，则此处已经置为空。 |
| 4. | 如果元组较多。那么内部连接比外部连接工作得更快。 | 通常，外部连接比内部连接慢。但除了一些特殊情况。 |
| 5. | 当我们需要任何特定属性的详细信息时，就会用到它。 | 当我们想要完成信息时，它就被使用了。 |
| 6. | JOIN 和 INNER JOIN 两个子句的工作原理相同。 | 完全外连接和完全连接这两个子句的工作原理是一样的。 |
| 7. | SQL 语法:
从表 1 INNER JOIN / JOIN 表 2
中选择*
ON table 1 . column _ name = table 2 . column _ name； |

</center>

SQL Syntax:
select *
from table1 LEFT OUTER JOIN / RIGHT OUTER JOIN /
FULL OUTER JOIN / FULL JOIN table2 ON
table1.column_name = table2.column_name;