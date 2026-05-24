# SQL 注释

> 原文: [https://www.geeksforgeeks.org/sql-comments/](https://www.geeksforgeeks.org/sql-comments/)

正如任何编程语言一样，注释在 SQL 中也很重要。在这一集中，我们将学习在任何 SQL 片段中编写注释。

注释可以用以下三种格式编写：

1.  单行注释。
2.  多行注释。
3.  行内注释。

## 单行注释

单行起止的注释视为单行注释。以 `--` 开头的行是注释，不会被执行。

语法：

```sql
-- single line comment
-- another comment
SELECT * FROM Customers;
```

## 多行注释

在一行开始并在另一行结束的注释被视为多行注释。以 `/*` 开头的行被视为注释的起点，当遇到 `*/` 时注释终止。

语法：

```sql
/* multi line comment
another comment */
SELECT * FROM Customers;
```

## 行内注释

行内注释是多行注释的扩展，注释可以写在语句中间，并被 `/*` 和 `*/` 包围。

语法：

```sql
SELECT * FROM /* Customers; */
```

更多示例：

```sql
Multi line comment ->
/* SELECT * FROM Students;
SELECT * FROM STUDENT_DETAILS;
SELECT * FROM Orders; */
SELECT * FROM Articles;

In line comment ->
SELECT * FROM Students;
SELECT * FROM /* STUDENT_DETAILS;
SELECT * FROM Orders;
SELECT * FROM */ Articles;
```

本文由 **[Pratik Agarwal](https://www.facebook.com/Pratik.Agarwal01)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 `contribute@geeksforgeeks.org`。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。