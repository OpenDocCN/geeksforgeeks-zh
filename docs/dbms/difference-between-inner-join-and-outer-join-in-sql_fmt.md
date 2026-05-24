# SQL 中内部连接和外部连接的区别

> 原文：`https://www.geeksforgeeks.org/difference-between-inner-join-and-outer-join-in-sql/`

## 1. 内部连接

是 SQL 中[连接](https://www.geeksforgeeks.org/sql-join-set-1-inner-left-right-and-full-joins/)操作的一种。内部联接是一种返回两个或多个表之间的组合元组的操作，其中至少有一个属性是公共的。如果表之间没有共同的属性，那么它将不返回任何内容。

**语法：**

```sql
select * 
from table1 INNER JOIN table2
on table1.column_name = table2.column_name;
```

或

```sql
select *
from table1 JOIN table2
on table1.column_name = table2.column_name;
```

## 2. 外部连接

外部连接是一种 SQL 中的连接操作。外部联接是一种操作，即使联接条件失败，它也会从指定的表中返回组合元组。在 SQL 中有三种类型的外部连接，即

1.  左外连接
2.  右外连接
3.  完全外部连接

**左外连接语法：**

```sql
select *
from table1 LEFT OUTER JOIN table2
on table1.column_name = table2.column_name;
```

**右外连接语法：**

```sql
select *
from table1 RIGHT OUTER JOIN table2
on table1.column_name = table2.column_name;
```

**完全外部连接的语法：**

```sql
select *
from table1 FULL OUTER JOIN table2
on table1.column_name = table2.column_name;
```

## 内部连接和外部连接的区别

下面是内部连接和外部连接之间的差异表：

<figure class="table">

| S.No | 内部连接 | 外部连接 |
| --- | --- | --- |
| 1. | 它返回两个或多个表之间的组合元组。 | 即使连接条件失败，它也会从指定的表中返回组合元组。 |
| 2. | 使用 `INNER JOIN` 和 `JOIN` 子句。 | 左外连接、右外连接、全外连接等。 |
| 3. | 当任何属性不常见时，它将不返回任何内容。 | 它不依赖于公共属性。如果该属性为空，则已经为空。 |
| 4. | 如果元组较多，那么内部连接比外部连接工作得更快。 | 通常，外部连接比内部连接慢。但除了一些特殊情况。 |
| 5. | 当我们需要任何特定属性的详细信息时，就会用到它。 | 当我们想要完成信息时，它就被使用了。 |
| 6. | `JOIN` 和 `INNER JOIN` 两个子句的工作原理相同。 | `FULL OUTER JOIN` 和 `FULL JOIN` 这两个子句的工作原理是一样的。 |
| 7. | SQL 语法：`SELECT * FROM table1 INNER JOIN / JOIN table2 ON table1.column_name = table2.column_name;` | SQL 语法：`SELECT * FROM table1 LEFT OUTER JOIN / RIGHT OUTER JOIN / FULL OUTER JOIN / FULL JOIN table2 ON table1.column_name = table2.column_name;` |

</figure>