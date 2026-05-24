# SQL | PL/SQL 中的过程

> 原文:[https://www.geeksforgeeks.org/sql-procedures/](https://www.geeksforgeeks.org/sql-procedures/)

PL/SQL 是一种块结构语言，它使开发人员能够将 SQL 的力量与过程语句结合起来。
PL/SQL 中的一个存储过程不过是一系列可以存储在数据库目录中的声明性 SQL 语句。一个过程可以被认为是一个函数或方法。它们可以通过触发器、其他过程或 Java、PHP 等上的应用程序来调用。
一个块的所有语句都一次性传递给 Oracle 引擎，这提高了处理速度，减少了流量。

**优势:**

*   它们提高了应用程序的性能。如果在单个连接中的应用程序中频繁调用某个过程，则传递该过程的编译版本。
*   它们减少了数据库和应用程序之间的流量，因为冗长的语句已经输入到数据库中，不需要通过应用程序一次又一次地发送。
*   它们增加了代码的可重用性，类似于函数和方法在其他语言如 C/C++和 Java 中的工作方式。

**缺点:**

*   存储过程会导致大量内存使用。数据库管理员应该决定特定应用程序可以使用多少存储过程的上限。
*   MySQL 不提供调试存储过程的功能。

**创建存储过程的语法**

```sql
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO

-- Comments --

CREATE PROCEDURE procedure_name
  = ,
  = ,
  = 

AS
BEGIN
-- Query --
END

GO

```

示例:

```sql
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO

CREATE PROCEDURE GetStudentDetails
      @StudentID int = 0
AS
BEGIN
      SET NOCOUNT ON;
      SELECT FirstName, LastName, BirthDate, City, Country
      FROM Students WHERE StudentID=@StudentID
END
GO

```

**修改现有存储过程的语法**

```sql
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO

-- Comments --

ALTER PROCEDURE procedure_name
  = ,
  = ,
  = 

AS
BEGIN
-- Query --
END

GO

```

示例:

```sql
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO

ALTER PROCEDURE GetStudentDetails
      @StudentID int = 0
AS
BEGIN
      SET NOCOUNT ON;
      SELECT FirstName, LastName, City
      FROM Students WHERE StudentID=@StudentID
END
GO

```

**删除程序的语法**:

```sql
DROP PROCEDURE procedure_name

```

示例:

```sql
DROP PROCEDURE GetStudentDetails

```

本文由 **Anannya Uberoi** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。