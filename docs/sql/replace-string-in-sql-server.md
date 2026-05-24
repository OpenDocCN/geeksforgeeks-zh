# 替换 SQL Server 中的字符串

> 原文:[https://www.geeksforgeeks.org/replace-string-in-sql-server/](https://www.geeksforgeeks.org/replace-string-in-sql-server/)

假设我们需要更新或替换任何表中的任何字符串值，我们可以使用以下方法–

*   **在 SQL Server 中替换字符串示例:**
    在下面的示例中，我们有一个字符串变量，然后我们将使用 Replace 函数用新字符串替换字符串的一部分。

**要替换字符串的 SQL Server 查询–**

```sql
DECLARE @String_Value varchar(50)
SET @String_Value = 'This provides free and excellent knowledge on SQL Server.'
SELECT REPLACE (@String_Value, 'This', 'Geeksforgeeks');
```

**输出:**

```sql
Geeksforgeeks provides free and excellent knowledge on SQL Server.
```

假设我们有一个名为“ **geek_demo** ”的下表:

| 名字 | 薪水 | 城市 | 电子邮件 |
| --- | --- | --- | --- |
| 鸭子！鸭子 | Twenty-four thousand five hundred | 德里 | ankit@xyz.com |
| 巴比塔 | Twenty-three thousand six hundred | 无聊死了 | babita@xyz.com |
| 车坛 | Twenty-five thousand six hundred | 无聊死了 | chetan@xyz.com |
| 迪帕克（男子名） | Twenty-four thousand three hundred | 德里 | deepak@xyz.com |
| 伊莎！伊莎 | Twenty-five thousand nine hundred | 德里 | isha@xyz.com(中文) |
| 库希 | Twenty-four thousand six hundred | 无聊死了 | khushi@xyz.com(中文) |
| 非常 | Twenty-five thousand five hundred | 无聊死了 | megha@xyz.com |
| 毛 | Twenty-three thousand nine hundred | 无聊死了 | parul@xyz.com |

*   **替换字符串示例:**
    在下面的示例中，我们将使用 Replace 函数替换 SQL Server SELECT 语句中的字符串，同时从 SQL Server 表中选择数据。

**替换部分字符串的 SQL Server 查询–**

```sql
SELECT TOP 1000 [Name], [Salary], [City], [email], 
REPLACE([email], 'xyz.com', 'gfg.org') AS [New EmailID]
FROM [geek_demo]
```

**输出:**

| 名字 | 薪水 | 城市 | 电子邮件 | 新电子邮件 ID |
| --- | --- | --- | --- | --- |
| 鸭子！鸭子 | Twenty-four thousand five hundred | 德里 | ankit@xyz.com | ankit@gfg.org |
| 巴比塔 | Twenty-three thousand six hundred | 无聊死了 | babita@xyz.com | babita@gfg.org |
| 车坛 | Twenty-five thousand six hundred | 无聊死了 | chetan@xyz.com | chetan@gfg.org |
| 迪帕克（男子名） | Twenty-four thousand three hundred | 德里 | deepak@xyz.com | deepak@gfg.org |
| 伊莎！伊莎 | Twenty-five thousand nine hundred | 德里 | isha@xyz.com(中文) | 伊莎@gfg.org |
| 库希 | Twenty-four thousand six hundred | 无聊死了 | khushi@xyz.com(中文) | khushi@gfg.org |
| 非常 | Twenty-five thousand five hundred | 无聊死了 | megha@xyz.com | megha@gfg.org |
| 毛 | Twenty-three thousand nine hundred | 无聊死了 | parul@xyz.com | parul@gfg.org |

*   **替换 SQL 语句中的字符串示例:**
    在下面的示例中，我们将使用 UPDATE 语句中的 Replace 函数替换 SQL UPDATE 语句中的字符串。

**替换部分字符串的 SQL Server 查询–**

```sql
UPDATE [geek_demo]
SET [email] = REPLACE([email], 'xyz.com', 'gfg.org');
```

**结果:**

```sql
(8 row(s) affected)
```

**现在让我们看看更新的表格–**

```sql
SELECT TOP 1000 [Name], [Salary], [City], [email]
FROM [geek_demo];
```

**输出:**

| 名字 | 薪水 | 城市 | 电子邮件 |
| --- | --- | --- | --- |
| 鸭子！鸭子 | Twenty-four thousand five hundred | 德里 | ankit@gfg.org |
| 巴比塔 | Twenty-five thousand six hundred | 无聊死了 | babita@gfg.org |
| 车坛 | Twenty-five thousand six hundred | 无聊死了 | chetan@gfg.org |
| 迪帕克（男子名） | Twenty-four thousand three hundred | 德里 | deepak@gfg.org |
| 伊莎！伊莎 | Twenty-five thousand nine hundred | 德里 | 伊莎@gfg.org |
| 库希 | Twenty-four thousand six hundred | 无聊死了 | khushi@gfg.org |
| 非常 | Twenty-five thousand five hundred | 无聊死了 | megha@gfg.org |
| 毛 | Twenty-three thousand nine hundred | 无聊死了 | parul@gfg.org |