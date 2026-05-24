# SQL | SEQUENCES

> 原文: [https://www.geeksforgeeks.org/sql-sequences/](https://www.geeksforgeeks.org/sql-sequences/)

Sequence 是一组整数 1，2，3，…，它们由一些数据库系统生成并支持，以便按需产生唯一的值。

*   序列是用户定义的模式绑定对象，它生成一系列数值。
*   序列在许多数据库中经常使用，因为许多应用程序要求表中的每一行都包含一个唯一的值，序列提供了一种简单的方法来生成它们。
*   数值序列以定义的间隔按升序或降序生成，并可配置为超过 `max_value` 时重新启动。

## 语法

```sql
CREATE SEQUENCE sequence_name
START WITH initial_value
INCREMENT BY increment_value
MINVALUE minimum_value
MAXVALUE maximum_value
CYCLE|NOCYCLE ;
```

*   `sequence_name`: 序列的名称。
*   `initial_value`: 序列开始的起始值。`initial_value` 应大于或等于最小值且小于等于最大值。
*   `increment_value`: 序列将自我递增的值。`increment_value` 可以是正数或负数。
*   `minimum_value`: 序列的最小值。
*   `maximum_value`: 序列的最大值。
*   `cycle`: 当序列达到其限制时，它从头开始。
*   `nocycle`: 如果序列超过其 `max_value`，将抛出异常。

## 示例

以下是按升序创建序列的序列查询。

### 示例 1

```sql
CREATE SEQUENCE sequence_1
START WITH 1
INCREMENT BY 1
MINVALUE 0
MAXVALUE 100
CYCLE;
```

以上查询将创建一个名为 `sequence_1` 的序列。序列将从 1 开始，并将增加 1，最大值为 100。超过 100 后，序列将从起始值开始重复。

### 示例 2

以下是按降序创建序列的序列查询。

```sql
CREATE SEQUENCE sequence_2
START WITH 100
INCREMENT BY -1
MINVALUE 1
MAXVALUE 100
CYCLE;
```

以上查询将创建一个名为 `sequence_2` 的序列。序列将从 100 开始，应小于或等于最大值，并将递增 -1，最小值为 1。

### 使用序列的示例

创建一个名为 `students` 的表，列名为 `id` 和 `name`。

```sql
CREATE TABLE students
(
    ID number(10),
    NAME char(20)
);
```

现在将值插入表中。

```sql
INSERT INTO students VALUES(sequence_1.nextval, 'Ramesh');
INSERT INTO students VALUES(sequence_1.nextval, 'Suresh');
```

其中 `sequence_1.nextval` 将以 `sequence_1` 中定义的序列在 `id` 列中插入 id。

输出:

```sql
 ______________________
| ID  |      NAME      |
------------------------
|  1  |     Ramesh     |
|  2  |     Suresh     |
 ----------------------
```

本文由 **[ARSHPREET SINGH](https://github.com/Arshpreet1997)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。