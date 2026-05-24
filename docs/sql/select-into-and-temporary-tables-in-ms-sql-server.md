# 在 MS SQL Server 中选择进入和临时表

> 原文:[https://www . geeksforgeeks . org/select-in-ms-SQL-server 表和临时表/](https://www.geeksforgeeks.org/select-into-and-temporary-tables-in-ms-sql-server/)

**1。选择进入:**
假设一个表有一些特定的行，必须转移到同一数据库的另一个表。可以使用**选择进入**语句，如下所示–

```sql
select list into destination from source (where condition) 
```

**例:**
有学生和分数两个表。学生的分数必须从分数转移到学生表。这必须按照以下步骤进行:

```sql
Select *
from student;
```

| 名字 | 罗龙 | 课程 |
| 玛雅人 | One hundred and eleven | 中学生毕业考试 |
| 奈纳 | One hundred and twelve | 欧洲经济委员会 |
| 警察 | One hundred and thirteen | 东方马脑脊髓炎 |
| [人名]克莱拉 | One hundred and fourteen | 技工 |

```sql
Select *
from marks;
```

| 名字 | 罗龙 | 米千克秒单位制的 |
| 玛雅人 | One hundred and eleven | eighty-five |
| 奈纳 | One hundred and twelve | Seventy-five |
| 警察 | One hundred and thirteen | Sixty-five |
| [人名]克莱拉 | One hundred and fourteen | Fifty-five |

```sql
Select mks into student 
from marks;
```

| 名字 | 罗龙 | 课程 | 米千克秒单位制的 |
| 玛雅人 | One hundred and eleven | 中学生毕业考试 | eighty-five |
| 奈纳 | One hundred and twelve | 欧洲经济委员会 | Seventy-five |
| 警察 | One hundred and thirteen | 东方马脑脊髓炎 | Sixty-five |
| [人名]克莱拉 | One hundred and fourteen | 技工 | Fifty-five |

分数将被添加到学生表格中。“where”子句可用于条件。它是可选的。

**2。临时表:**
用户有时希望根据给定的表值创建一个单独的表。这必须使用临时表的概念来完成。可以通过两种方式创建临时表:使用创建表语法或选择进入语法。

**选择进入:**
必须使用选择进入语句从学生表创建一个新表，如下所示:

```sql
Select *
from student;
```

| 名字 | 罗龙 | 课程 |
| 玛雅人 | One hundred and eleven | 中学生毕业考试 |
| 奈纳 | One hundred and twelve | 欧洲经济委员会 |
| 警察 | One hundred and thirteen | 东方马脑脊髓炎 |
| [人名]克莱拉 | One hundred and fourteen | 技工 |

```sql
Select name, rollno into temp_table #details 
from student;
```

| 名字 | 罗龙 |
| 玛雅人 | One hundred and eleven |
| 奈纳 | One hundred and twelve |
| 警察 | One hundred and thirteen |
| [人名]克莱拉 | One hundred and fourteen |

**创建表:**
可以使用创建表语句创建新表:

```sql
Create table #details( name varchar2(30), rollno int);
```

将创建一个新表。这些值可以从其他表中复制，如下所示:

**插入到#details 中选择姓名，rollno 来自学生；**

| 名字 | 罗龙 |
| 玛雅人 | One hundred and eleven |
| 奈纳 | One hundred and twelve |
| 警察 | One hundred and thirteen |
| [人名]克莱拉 | One hundred and fourteen |