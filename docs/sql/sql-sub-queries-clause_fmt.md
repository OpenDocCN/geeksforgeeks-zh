# SQL FROM子句中的子查询

> 原文: [https://www.geeksforgeeks.org/sql-sub-queries-clause/](https://www.geeksforgeeks.org/sql-sub-queries-clause/)

`FROM`子句可用于在SQL中指定子查询表达式。子查询产生的关系然后被用作外部查询所应用的新关系。

*   大多数SQL实现都支持`FROM`子句中的子查询。
*   `FROM`子句中关系的相关变量不能用于`FROM`子句中的子查询。

## 语法

```sql
SELECT column1, column2 FROM 
(SELECT column_x  as C1, column_y FROM table WHERE PREDICATE_X)
as table2
WHERE PREDICATE;
```

## 注意

首先对`FROM`子句中的子查询进行求值，然后将求值结果存储在一个新的临时关系中。
接下来，评估外部查询，仅从满足外部查询`WHERE`子句中谓词的临时关系中选择那些元组。

## 查询示例

### 例1

找到所有工资大于所有院系平均预算的教授。

**Instructor**关系:

| ID | NAME | DEPARTMENT | SALARY |
| :--- | :--- | :--- | :--- |
| 10101 | 史密斯 | 计算机科学 | 95000 |
| 12121 | 账单 | 电气工程 | 55000 |
| 15151 | 萨姆 | 人文学科 | 44000 |
| 22222 | 埃里克 | 机械工程 | 80000 |
| 33456 | 蜜蜂花 | 信息技术 | 65000 |
| 58583 | 耶那 | 公民工程 | 50000 |

**Department**关系:

| DEPARTMENT_NAME | BUDGET |
| :--- | :--- |
| 计算机科学 | 100000 |
| 电气工程 | 80000 |
| 人文学科 | 50000 |
| 机械工程 | 40000 |
| 信息技术 | 90000 |
| 公民工程 | 60000 |

### 查询

```sql
select I.ID, I.NAME, I.DEPARTMENT, I.SALARY from
(select avg(BUDGET) as averageBudget from DEPARTMENT) as BUDGET, Instructor as I
where I.SALARY > BUDGET.averageBudget;
```

### 输出

| ID | NAME | DEPARTMENT | SALARY |
| :--- | :--- | :--- | :--- |
| 10101 | 史密斯 | 计算机科学 | 95000 |
| 22222 | 埃里克 | 机械工程 | 80000 |

### 说明

从`Department`关系来看，各部门的平均预算是70000。埃里克和史密斯是`Instructor`关系中唯一工资超过70000的讲师，因此出现在输出关系中。