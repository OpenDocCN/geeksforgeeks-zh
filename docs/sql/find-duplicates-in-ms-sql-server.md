# 在 MS SQL Server 中查找重复项

> 原文:[https://www . geesforgeks . org/find-duplicates-in-ms-SQL-server/](https://www.geeksforgeeks.org/find-duplicates-in-ms-sql-server/)

我们可以使用以下方法来查找表中的重复值。

*   分组依据条款。
*   ROW_NUMBER()函数。

**1。使用 GROUP BY 子句查找重复值:**

**语法:**

```sql
SELECT col1, col2, ...COUNT(*)
FROM table_name
GROUP BY col1, col2, ...
HAVING COUNT(*) > 1;
```

**示例–**
让我们创建一个名为 Geek 的表，该表包含三列 ID、A 和 b

```sql
CREATE TABLE Geek (
ID INT IDENTITY(1, 1),
A INT,
B INT,
PRIMARY KEY(id));
```

让我们给 Geek 表增加一些值–

```sql
INSERT INTO Geek (A, B)
VALUES (1, 1),(1, 2), (1, 3), (2, 1),
(1, 2), (1, 3), (2, 1), (2, 2);
```

我们知道 Geek 表包含以下重复行–

```sql
(1, 2) (2, 1) (1, 3) 
```

使用极客表中的分组依据子句查找重复行的微软 SQL Server 查询:

```sql
SELECT A, B, COUNT(*) AS num
FROM Geek
GROUP BY A, B
HAVING COUNT(*) > 1;
```

**输出–**

**表–**极客

| A | B | 数字 |
| --- | --- | --- |
| Two | one | Two |
| one | Two | Two |
| one | three | Two |

要查找每个重复行的完整行详细信息，请使用 CTE 将上述查询的输出与 Geek 表连接起来:

```sql
WITH CTE AS ( 
SELECT A, B, COUNT(*) AS num
FROM Geek
GROUP BY A, B
HAVING COUNT(*) > 1
)
SELECT Geek.ID, Geek.A, Geek.B
FROM Geek
INNER JOIN CTE ON
CTE.A = Geek.A AND CTE.B = Geek.B
ORDER BY Geek.A, Geek.B;
```

**输出–**

**表–**极客

| 身份证明 | A | B |
| --- | --- | --- |
| Two | one | Two |
| five | one | Two |
| six | one | three |
| three | one | three |
| four | Two | one |
| seven | Two | one |

**2。使用 ROW_NUMBER()函数查找重复值:**

**语法:**

```sql
WITH cte AS (
SELECT col,ROW_NUMBER() OVER (
PARTITION BY col
ORDER BY col) AS row_num
FROM table_name
)  
SELECT * 
FROM cte  
WHERE row_num > 1;
```

使用极客表中的 ROW_NUMBER()函数查找重复行的 MS SQL Server 查询:

```sql
WITH CTE AS (
SELECT A, B,
ROW_NUMBER() OVER (
PARTITION BY A, B
ORDER BY A, B
) AS rownum
FROM Geek
)
SELECT *
FROM CTE
WHERE rownum > 1;
```

**输出–**

**表–**极客

| A | B | 行 |
| --- | --- | --- |
| one | Two | Two |
| one | three | Two |
| Two | one | Two |