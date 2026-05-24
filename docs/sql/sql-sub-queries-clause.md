# 从条款

中的 SQL |子查询

> 原文:[https://www.geeksforgeeks.org/sql-sub-queries-clause/](https://www.geeksforgeeks.org/sql-sub-queries-clause/)

From 子句可用于在 SQL 中指定子查询表达式。子查询产生的关系然后被用作外部查询所应用的新关系。

*   大多数 SQL 实现都支持 from 子句中的子查询。
*   from 子句中关系的相关变量不能用于 from 子句中的子查询。

**<u>语法</u> :**

```sql
SELECT column1, column2 FROM 
(SELECT column_x  as C1, column_y FROM table WHERE PREDICATE_X)
as table2
WHERE PREDICATE;
```

**<u>注意</u> :** 首先对 from 子句中的子查询进行求值，然后将求值结果存储在一个新的临时关系中。
接下来，评估外部查询，仅从满足外部查询 where 子句中谓词的临时关系中选择那些元组。

**<u>查询</u>**

**<u>例 1</u> :** 找到所有工资大于所有院系平均预算的教授。

**讲师**关系:

| 说明 ID | 名字 | 部门 | 薪水 |
| Forty-four thousand five hundred and forty-seven | 史密斯（姓氏） | 计算机科学 | Ninety-five thousand |
| Forty-four thousand five hundred and forty-one | 账单 | 与电有关的 | Fifty-five thousand |
| Forty-seven thousand seven hundred and seventy-eight | 萨姆（男子名） | 人文学科 | Forty-four thousand |
| Forty-eight thousand one hundred and forty-seven | 埃里克 | 机械的 | Eighty thousand |
| Four hundred and eleven thousand five hundred and forty-seven | 蜜蜂花 | 信息技术 | Sixty-five thousand |
| Forty-eight thousand eight hundred and ninety-eight | 耶那 | 公民的 | Fifty thousand |

**部门**关系:

| 部门名称 | 预算 |
| 计算机科学 | One hundred thousand |
| 与电有关的 | Eighty thousand |
| 人文学科 | Fifty thousand |
| 机械的 | forty thousand |
| 信息技术 | Ninety thousand |
| 公民的 | Sixty thousand |

**<u>查询</u> :**

```sql
select I.ID, I.NAME, I.DEPARTMENT, I.SALARY from
**(select avg(BUDGET) as averageBudget from DEPARTMENT) as BUDGET, Instructor as I**
where I.SALARY > BUDGET.averageBudget;
```

**<u>输出</u>**

| 说明 ID | 名字 | 部门 | 薪水 |
| Forty-four thousand five hundred and forty-seven | 史密斯（姓氏） | 计算机科学 | Ninety-five thousand |
| Forty-eight thousand one hundred and forty-seven | 埃里克 | 机械的 | Eighty thousand |

**<u>说明</u> :** 从部门关系来看，各部门的平均预算是 7 万。埃里克和史密斯是讲师关系中唯一工资超过 70000 英镑的讲师，因此出现在输出关系中。