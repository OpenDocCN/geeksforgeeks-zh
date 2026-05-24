# MS SQL Server 中的更新动作

> 原文:[https://www . geesforgeks . org/update-action-in-ms-SQL-server/](https://www.geeksforgeeks.org/update-action-in-ms-sql-server/)

**引用操作**允许用户更新或删除父表中的列。如果从父表中删除一列，它将立即从子表中删除。

**语法:**

```sql
foreign key (foreign-key_constraint) 
references parent_table (parentkey_column) 
ON Update Action
```

考虑两个表——来自大学数据库的学生(父表)和分数(子表)。如果用户想要更新一个列，那么必须按照以下步骤进行

<center>
**Table –** Student</center>

| 名字 | 辊号 | 课程 |
| --- | --- | --- |
| 玛雅人 | One hundred and eleven | 中学生毕业考试 |
| 里亚 | One hundred and twelve | 技工 |

<center>
**Table –** Marks

| 名字 | 辊号 | 马克斯（英格兰人姓氏） |
| --- | --- | --- |
| 玛雅人 | One hundred and eleven | Eight point nine |
| 里亚 | One hundred and twelve | Seven point nine |

</center>

对表执行更新操作的 SQL 查询是:

```sql
foreign key references 
Student(rollnumber) 
ON Update Action
```

**输出–**

<center>
**Table –** Student

| 名字 | 辊号 | 课程 |
| --- | --- | --- |
| 玛雅人 | One hundred and ten | 中学生毕业考试 |
| 里亚 | One hundred and eleven | 技工 |

</center>

<center>
**Table –** Marks

| 名字 | 辊号 | 马克斯（英格兰人姓氏） |
| --- | --- | --- |
| 玛雅人 | One hundred and ten | Eight point nine |
| 里亚 | One hundred and eleven | Seven point nine |

</center>

这也会更新整个父表和子表中的 rollnumber 列。在语法中，约束不是必须包含的术语。必要时可以使用。还有其他允许的操作–无操作、级联、设置 null、设置默认值。

*   **更新时无操作–**
    它会引发一个错误，并回滚父表的更新操作。
*   **在更新级联时–**
    级联操作更新父表和子表中的所有行。
*   **更新时设置为空–**
    只有当外键可为空时，父表和子表中的行才设置为空。
*   **更新时设置默认值–**
    只有当外键有默认定义时，相应的父表行才会更新，此时子表行将被设置为默认值。