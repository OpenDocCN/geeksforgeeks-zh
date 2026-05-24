# SQL 中的不等式运算符

> 原文:[https://www.geeksforgeeks.org/inequality-operator-in-sql/](https://www.geeksforgeeks.org/inequality-operator-in-sql/)

在本文中，我们将讨论 SQL 中运算符的概述，并且我们的重点将是 SQL 中的不等式运算符。我们一个一个来讨论。

**先决条件–**[SQL 中的运算符](https://www.geeksforgeeks.org/sql-arithmetic-operators/)

**概述:**
SQL 运算符广泛用于根据条件访问信息。在不等式运算符中，我们将检查特定列的条件。SQL 中的运算符用于执行条件，在条件的基础上，输出就会到来。例如，如果您想从数据库中查找数据，比如说学生姓名，那么您可以使用一个相等的运算符来检查姓名。不等式运算符是 SQL 语句 WHERE 子句中用来比较两个元素的保留字。

**示例–**
在本例中，假设您想从数据库的学生表中访问学生姓名。因此，我们将在 WHERE 子句中使用相等运算符，如下所示。

```sql
Select * from student where name = 'ABC';
```

**SQL 中的不等式运算符:**
有时当我们想要选择不满足某个条件的数据时，就像所有不在第二年<sup>和第二年</sup>的学生一样。请参考下表。在这个表中，学生是表名和姓名，年份、科目是表的列名。

<figure class="table">T21**科目**T29】Anish MandalT37】Youbraj Rai

| student |
| --- |
| **Name** | **year** |
| --- | --- |
| four | Compiler design |
|  |

</figure>

**例-1 :**
所以要选择那些不在第二年的人。因此，在这里，我们将使用如下不等式运算符。

```sql
SELECT * FROM students WHERE year <> 2;
```

**输出:**
将有 2 条记录被选中。这些是您应该从以下任一 SQL 语句中看到的结果。

*   和之前一样，我们先用 ***** **选择所有物品。**这将给我们所有年份的学生。
*   自从**年< > 2** 在**年**栏中用 **2** 过滤掉学生项目后，我们只得到一个第四年的学生。

<figure class="table">

| **结果** |
| --- |
| **名称** | **年** | **受试者** |
| --- | --- | --- |
| Anish Mandal | four | 编译程序设计 |
| 尤布兰·瑞 | four | Java 语言(一种计算机语言，尤用于创建网站) |

</figure>

**示例-2 :**
我们还可以使用带文本值的不等式运算符，比如在**【Java】中获取所有不主语的学生。**

```sql
SELECT * FROM students WHERE subjects <> 'Java';
```

将选择 2 条记录，即“编译器设计”、“Php”。这些是您应该看到的任何一条 SQL 语句的结果。在该示例中，两个 SELECT 语句都将返回**主题**表中主题不等于 Java 的所有行。

<figure class="table">T36】Swatee 维尔马

| **Score** |
| --- |
| **Name** | **year** | T21] subjects |
| --- | --- | --- |
| 安妮斯 | four | Compiler design |
| Two |

</figure>

**使用:**
要检查一列的值是否不等于另一列，我们使用不等式运算符 **< >。**

**注:**

1.  不等式运算符<>可以用什么样的值？
    Ans-任何一种像文字和数字。

2.  不等式符号什么时候有用？
    Ans-当你想要得到所有不满足某个标准的物品时。