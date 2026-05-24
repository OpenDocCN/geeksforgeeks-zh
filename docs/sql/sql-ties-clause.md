# SQL |带关系子句

> 原文:[https://www.geeksforgeeks.org/sql-ties-clause/](https://www.geeksforgeeks.org/sql-ties-clause/)

此帖子是 [SQL 偏移量获取子句](https://www.geeksforgeeks.org/sql-offset-fetch-clause/)的延续

现在，我们了解了如何在 Oracle 数据库中使用 Fetch 子句以及指定的偏移量，并且我们还了解 Fetch 子句是 Oracle 数据库 12c 中新添加的子句，或者是 Oracle 数据库 12c 中添加的新功能。

现在考虑下面的例子:

假设我们有一个名为 **myTable** 的表，其数据如下:

```sql
ID    NAME        SALARY
-----------------------------
1    Geeks      10000
4    Finch      10000
2    RR         6000
3    Dhoni      16000
5    Karthik    7000
6    Watson     10000
```

现在，假设我们希望前三行按薪资降序排序，那么必须执行以下查询:

```sql

Query:
SELECT * from myTable 
order by salary desc 
fetch first 3 rows only;

Output: 
We got only first 3 rows order by Salary in Descending Order

ID    NAME    SALARY
--------------------------
3    Dhoni    16000
1    Geeks    10000
4    Finch    10000

```

**注**:在上面的结果中，我们得到了前 3 行，按薪资降序排列，但是我们还有一行薪资相同，即名称为**沃森**和薪资 **10000** 的行，但是没有出现，因为我们只将输出限制在前三行。但这并不是最优的，因为在实时应用程序中，我们大部分时间都需要显示绑定的行。

**现实生活中的例子**–假设我们有 10 名赛车手在跑，我们只有 3 个奖，即第一、第二、第三名，但是假设赛车手 3 和 4 在同一时间一起完成了比赛，那么在这种情况下，我们在 3 和 4 之间有一个平局，这就是为什么两个人都是位置 3 的持有者。

### 

带领带

因此，为了克服上述问题，甲骨文引入了一个名为**与**条款的条款。现在，让我们看看前面使用 With Ties 子句的例子。

```sql
Query:
SELECT * from myTable 
order by salary desc 
fetch first 3 rows With Ties;

Output:
See we get only first 3 rows order by Salary in Descending Order along with Tied Row also

ID    NAME       SALARY
--------------------------
3    Dhoni     16000
1    Geeks     10000
6    Watson    10000 // We get Tied Row also
4    Finch     10000

```

现在，看我们得到了**并列排**，这也是我们以前没有得到的。

**注意**:我们**在我们的输出中得到**并列行，只有当我们在我们的 Select 语句中使用 **order by** 子句时。假设，如果我们不使用 order by 子句，并且仍然使用带有 ties 的**子句，那么我们将不会在输出中获得并列行，并且查询的行为与使用 with ties 子句的 **ONLY** 子句**而不是**相同。**

****示例**–假设我们执行以下查询(不使用 order by 子句):**

```sql
**Query**:
SELECT * from myTable 
fetch first 3 rows **With Ties**;

**Output**:
See we won't get the tied row because we didn't use order by clause

ID    NAME      SALARY
--------------------------
1    Geeks    10000
4    Finch    10000
2    RR       6000 
```

**在上面的结果中，我们不会得到并列的行，我们只得到前 3 行。因此**与**的关系是**通过**子句将与**的订单联系在一起，也就是说，当且仅当我们将**与**子句一起使用时，我们会在输出中获得被联系的行。****

****注意**:请确保在 Oracle Database 12c 中运行这些查询，因为 Fetch 子句是 Oracle 12c 中新增加的功能，同样 With Ties 只在 Oracle Database 12c 中运行，这些查询**不会**在 10g 或 11g 等 12c 以下版本中运行。**

****参考** s: [关于提取子句以及与关系子句](https://oracle-base.com/articles/12c/row-limiting-clause-for-top-n-queries-12cr1)，[在线执行 SQL 查询](https://livesql.oracle.com/apex/livesql/file/index.html)**