# 在 SQL Server 中交换列值

> 原文:[https://www . geesforgeks . org/swap-column-values-in-SQL-server/](https://www.geeksforgeeks.org/swap-column-values-in-sql-server/)

**简介(交换 SQL Server 中的列值):**
如果您是开发人员，并且已经学习了编程语言，您可能会认为您需要第三个变量或另一个临时存储位置来交换这些值。在这里，由于您是一个 SQL Server 数据库管理员，您可以简单地使用一个更新语句来交换它们。

**示例和应用程序功能:**
碰巧 SQL 用户可能在数据库列中输入了不正确的值，下一个任务是交换这些值。

**语法:**
语法写一个查询来交换 SQL server 中的列值。

```sql
UPDATE [tablename]
SET [col1] = [col2],
   [col2] = [col1]
GO

```

让我们假设我们需要交换 SQL 服务器中任何表中的列。

**示例–**
让我们假设我们在表下方有“geek_demo”。

```sql
Select * from geek_demo ;

```

**输出:**

<figure class="table">电子邮件

|  | 【 load name 】 | 【名字】 | 【城市】 |
| --- | --- | --- | --- |

</figure>

现在，要更新列或交换列，请使用下面给出的查询。

```sql
UPDATE [geek_demo]
SET [FirstName] = [LastName], 
[LastName] = [FirstName]
GO

```

现在，让我们看看输出。

```sql
Select * from geek_demo ;
```

**输出:**

<figure class="table">

|  | 【名字】 | 【姓氏】 | 【电子邮件】 |
| --- | --- | --- | --- |

</figure>