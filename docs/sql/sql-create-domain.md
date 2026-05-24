# SQL |创建域

> 原文:[https://www.geeksforgeeks.org/sql-create-domain/](https://www.geeksforgeeks.org/sql-create-domain/)

**用于:Postgre sql**
CREATE DOMAIN 创建一个新的域。域本质上是一种带有可选约束(对允许的值集的限制)的数据类型。定义域的用户成为域的所有者。

域对于将字段的公共约束抽象到单个位置进行维护非常有用。例如，几个表可能包含电子邮件地址列，都需要相同的 CHECK 约束来验证地址语法。定义一个域，而不是单独设置每个表的约束。

**示例:**

```sql
CREATE DOMAIN CPI_DATA AS REAL CHECK
(value >= 0 AND value <= 10);

```

现在创建了 CPI_DATA 域，因此我们可以在任何数据库表中使用这个域，如下所示:

```sql
CREATE TABLE student(
sid char(9) PRIMARY KEY,
name varchar(30),
cpi CPI_DATA
);

```

每次 cpi_data 都会检查约束，当你在学生表中添加数据的时候。

**例 1 :**

```sql
Insert into student values (201501408,Raj,7.5); 
This will not violate the property of cpi. 

```

**例 2 :**

```sql
Insert into student values (201501188,Dhaval,12); 
```

ERROR。这将违反 cpi 的属性。

本文由 **Dhavalkumar Prajapati** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。