# 如何在 SQL 中使用带有聚合函数的 SELECT？

> 原文:[https://www . geesforgeks . org/如何使用 sql 中的聚合函数选择/](https://www.geeksforgeeks.org/how-to-use-select-with-aggregate-functions-in-sql/)

在 SQL 中，主要提供了五个[聚合函数](https://www.geeksforgeeks.org/aggregate-functions-in-sql/)。这些有助于我们以期望的方式处理表数据。所有这些都说明如下。在本文中，我们将使用微软的 SQL Server 作为我们的数据库。

**步骤 1:** 创建数据库。为此，使用下面的命令创建一个名为 GeeksForGeeks 的数据库。

**查询:**

```sql
CREATE DATABASE GeeksForGeeks
```

**输出:**

![](img/d2cfe8b2f31124d9744d03213361f840.png)

**步骤 2:** 使用 GeeksForGeeks 数据库。为此，请使用以下命令。

**查询:**

```sql
USE GeeksForGeeks
```

**输出:**

![](img/764b7f0286d9dc6812e0e8907809ffc3.png)

**步骤 3:** 在数据库 GeeksForGeeks 中创建一个表 END_SEM。该表有 3 列，即 S_NAME、ROLL 和 MARKS，包含姓名、卷号和不同学生的分数。

**查询:**

```sql
CREATE TABLE END_SEM(
S_NAME VARCHAR(20),
ROLL INT,
MARKS INT);
```

**输出:**

![](img/d6378d224b43ef998b9fa0689953ec94.png)

**第四步:**描述表 END_sEM 的结构。

**查询:**

```sql
EXEC SP_COLUMNS END_SEM;
```

**输出:**

![](img/fff34c4a6fbd43201e0a9b25cfa73ae0.png)

**第 5 步:**在 END_SEM 表中插入 5 行。

**查询:**

```sql
INSERT INTO END_SEM VALUES('ABE',1,99);
INSERT INTO END_SEM VALUES('SAM',2,87);
INSERT INTO END_SEM VALUES('DARREN',3,74);
INSERT INTO END_SEM VALUES('RACHEL',4,91);
INSERT INTO END_SEM VALUES('DWIGHT',5,56);
INSERT INTO END_SEM VALUES('ANGELA',6,45);
INSERT INTO END_SEM VALUES('CREED',7,33);
INSERT INTO END_SEM VALUES('GABE',8,64);
INSERT INTO END_SEM VALUES('KELLY',9,49);
INSERT INTO END_SEM VALUES('ERIN',10,80);
```

**输出:**

![](img/a742fb0f93d32123c6c500c2b3db68c8.png)

**第 6 步:**显示 END_SEM 表的所有行。

**查询:**

```sql
SELECT * FROM END_SEM;
```

**输出:**

![](img/f1d1475aa8a3dba8d73ecd9a3467c545.png)

SQL 中有五个[聚合函数](https://www.geeksforgeeks.org/aggregate-functions-in-sql/)。以上新创建的 **END_SEM** 表格展示了它们的用法:

*   **SUM 函数:**返回 **SUM** 后括号中指定的列的所有条目的和(相加)。

**查询:**

```sql
SELECT SUM(MARKS) AS "SUM OF MARKS" FROM END_SEM;
```

**输出:**

![](img/7d35adf4f545b87ec5fbb3b6a1e8572b.png)

*   **计数功能:**返回**计数**后括号中指定的列中非空条目的计数(个数)。如果所有的列都需要这个，那么我们需要在**计数**之后的括号中加上一个*号。

**查询:**

```sql
SELECT COUNT(MARKS) AS "COUNT OF
MARKS" FROM END_SEM;
```

**输出:**

![](img/2d6ce63c3b1508a6624e568d7716be44.png)

*   **AVG 函数:**返回 **AVG** 后括号内指定列所有条目的平均值(均值)。平均值=总和/计数

**查询 1:**

```sql
SELECT AVG(MARKS) AS "AVERAGE OF MARKS" FROM END_SEM;
```

**输出:**

![](img/f4073ce8214aefc403cda9bb68b348d6.png)

**查询 2:**

```sql
SELECT SUM(MARKS)/COUNT(MARKS) AS "AVERAGE OF MARKS" FROM END_SEM;
```

**输出:**

![](img/ba6b817478b13d0eb6b75dcace03da68.png)

*   **MAX 函数:**返回 **MAX** 后括号中指定的列中所有条目的最大值条目。

**查询:**

```sql
SELECT MAX(MARKS) AS "MAXIMUM OF MARKS" FROM END_SEM;
```

**输出:**

![](img/8a5c428bbda7e111ff14369fe46f91a6.png)

*   **MIN 函数:**返回 **MIN** 后括号中指定的列中所有条目的最小值条目。

**查询:**

```sql
SELECT MIN(MARKS) AS "MINIMUM OF MARKS" FROM END_SEM;
```

**输出:**

![](img/7af8eacd586debf47f21be389566029e.png)