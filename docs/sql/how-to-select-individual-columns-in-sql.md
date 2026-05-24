# 如何在 SQL 中选择单个列？

> 原文:[https://www . geesforgeks . org/如何选择 sql 中的单个列/](https://www.geeksforgeeks.org/how-to-select-individual-columns-in-sql/)

在 SQL 中，有时我们需要从表中选择单独的列。为此，我们使用一种特定的查询，如下面的演示所示。在本文中，我们将使用微软的 SQL Server 作为我们的数据库和选择关键字。 [选择](https://www.geeksforgeeks.org/sql-select-query/#:~:text=Select%20is%20the%20most%20commonly,fetch%20data%20from%20a%20database.&text=Learn%20SQL%20for%20interviews%20using,that%20the%20database%20server%20evaluates.) 是 SQL 中最常用的语句。SQL 中的 SELECT 语句用于从数据库中检索或获取数据。我们可以获取整个表，也可以根据特定的规则获取。返回的数据存储在结果表中。该结果表也称为结果集。

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

**步骤 3:** 在数据库 GeeksForGeeks 中创建一个居民表。该表有 3 列，即 R_NAME、AGE 和 FLAT，包含姓名、年龄和社会各种居民的固定数字。

**查询:**

```sql
CREATE TABLE RESIDENTS(
R_NAME VARCHAR(20),
AGE INT,
FLAT INT);
```

**输出:**

![](img/7049949768923f99bf86748ac3156f3c.png)

**第 4 步:**描述表格 RESIDENTS 的结构。

**查询:**

```sql
EXEC SP_COLUMNS RESIDENTS;
```

**输出:**

![](img/fc3410032581cb689ae715957eeb8719.png)

**第 5 步:**在 RESIDENTS 表中插入 5 行。

**查询:**

```sql
INSERT INTO RESIDENTS VALUES('MICHAEL',45,904);
INSERT INTO RESIDENTS VALUES('GARY',90,1105);
INSERT INTO RESIDENTS VALUES('SCOTT',39,806);
INSERT INTO RESIDENTS VALUES('JIM',34,301);
INSERT INTO RESIDENTS VALUES('PAMELA',29,502);
```

**输出:**

![](img/5de876419ecba8d446987c54917efac3.png)

**第 6 步:**显示居民表的所有行。

**查询:**

```sql
SELECT * FROM RESIDENTS;
```

**输出:**

![](img/92892396cdd90ed58cb04b1b34ea758b.png)

**第 7 步:**要从表中选择一个单独的列，我们需要在关键字 **SELECT** 后面加上要选择的列名，然后是查询的其余部分。例如，在下图中，列 **R_NAME** 是从表**居民**中选择的单个列。

**语法:**

```sql
SELECT COLUMN_NAME FROM TABLE_NAME;
```

**查询:**

```sql
SELECT R_NAME FROM RESIDENTS;
```

**输出:**

![](img/5e7931c9fa36e6b2a2ab221ce9522794.png)

**第八步:**

从表格**居民中选择个人栏**年龄**。**

**查询:**

```sql
SELECT AGE FROM RESIDENTS;
```

**输出:**

![](img/d2a72f68c4ea54b53b956cc7c4484894.png)

**第九步:**

从表格**居民**中选择单个列**平面**。

**查询:**

```sql
SELECT FLAT FROM RESIDENTS;
```

**输出:**

![](img/9589e9039b1ed664d36333aae8c014e9.png)