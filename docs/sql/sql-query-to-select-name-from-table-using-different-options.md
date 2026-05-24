# SQL |使用不同选项从表中选择名称的查询

> 原文:[https://www . geesforgeks . org/SQL-查询-从表中选择名称-使用不同的选项/](https://www.geeksforgeeks.org/sql-query-to-select-name-from-table-using-different-options/)

让我们考虑下面这张名为“**极客**”的表格:

<center>T15】莫汉 T17】阿罗拉 T19】DBAT21T25】妮莎 T29】AdminT32T77】Kumar

| G _ ID | 西方人名的第一个字 | 姓 | 部门 |
| --- | --- | --- | --- |
| one |
| Two | Verma |
| three | 管理 |
| six | Vinod | 地万 | 回顾 |
| seven | 片状 | 回顾 |
| eight |

</center>

使用别名作为名称从极客表中写入“名字”的 SQL 查询。

```sql
Select FIRSTNAME AS NAME 
from Geeks;
```

**输出–**

【莫汉】

| 【 name 】 |
| --- |
| 【妮莎】 |
| --- |

用大写字母从极客表中写出“名字”的 SQL 查询。

```sql
Select upper(FIRSTNAME) 
from Geeks;
```

**输出–**

| (No column name) |
| --- |
| [Mohan] |
| 【妮莎】 |

从极客表中查找 FIRSTNAME 前三个字符的 SQL 查询。

```sql
Select substring(FIRSTNAME, 1, 3) 
from Geeks;
```

**输出–**

| (No column name) |
| --- |
| 【卫生部】 |
| 【NIS】 |

将极客表中的名字和姓氏写入带有空格字符的单列 COMPLETENAME 的 SQL 查询应该将它们分开。

```sql
Select CONCAT(FIRSTNAME, ' ', LASTNAME) AS 'COMPLETENAME' 
from Geeks;
```

**输出–**

| full name |
| --- |
| 【莫汉·阿罗拉】 |
| 【nisha Verma】 |

编写一个 SQL 查询，按照名字升序打印极客表中的所有工作人员详细信息。

```sql
Select * 
from Geeks 
order by FIRSTNAME asc;
```

**输出–**

<center>T15】前岛亚美 T17】辛格 T19】作家 T21T23】8T25】吉塔 T27】肖安T32T77】Diwan

| G _ ID | 西方人名的第一个字 | 姓 | 部门 |
| --- | --- | --- | --- |
| four |
| 管理 |
| one | 管理 |
| seven | 片状 | 库马尔 | 回顾 |
| six | Vinod | 回顾 |
|  |

</center>