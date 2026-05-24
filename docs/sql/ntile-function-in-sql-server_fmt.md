# SQL Server 中的 NTILE()函数

> 原文:[https://www.geeksforgeeks.org/ntile-function-in-sql-server/](https://www.geeksforgeeks.org/ntile-function-in-sql-server/)

``NTILE()`` 函数在 [SQL Server](https://www.geeksforgeeks.org/sql-tutorial/) 中是一个窗口函数，它将有序分区的行分配到预定义数量的大致相等的组中。它为每个组分配一个范围为 1 的 ``number_expression``。 ``NTILE()`` 函数为该行所属的组中的每一行分配一个 ``number_expression``。

**语法:**

```sql
NTILE(number_expression) OVER (
   [PARTITION BY partition_expression ]
   ORDER BY sort_expression [ASC | DESC]
)
```

**详细语法参数:**

*   ``number_expression``
    ``number_expression`` 是行被分成的整数。
*   ``PARTITION BY`` 子句
    ``PARTITION BY`` 是可选的，它将结果集的行划分为使用 ``NTILE()``函数的分区。
*   ``ORDER BY`` 子句
    ``ORDER BY`` 子句定义了使用 ``NTILE()`` 的每个分区中行的顺序。

当行数不能被 ``number_expression`` 整除时，``NTILE()``函数会将两个大小的组的差除以 1。在 ``OVER()``子句中的 ``ORDER BY`` 指定的顺序中，较大的组总是在较小的组之前。此外，当所有行都可以被 ``number_expression`` 整除时，该函数会在 ``number_expression`` 中平均分配行。

**示例:**
让我们创建一个名为 ``geeks_demo`` 的表:

```sql
CREATE TABLE geeks_demo (
ID INT NOT NULL );
INSERT INTO geeks_demo(ID)
VALUES(1), (2), (3), (4), (5), (6), (7), (8), (9), (10);
```

现在，

```sql
SELECT * 
FROM geeks_demo;
```

| ID |
| --- |
| 1 |
| 2 |
| 3 |
| 4 |
| 5 |
| 6 |
| 7 |
| 8 |
| 9 |
| 10 |

### 1. 使用 ``NTILE()`` 函数将上述行分成 3 组：

```sql
SELECT ID,
NTILE (3) OVER (
ORDER BY ID
) Group_number
FROM geeks_demo; 
```

**输出:**

| ID | Group_number |
| --- | --- |
| 1 | 1 |
| 2 | 1 |
| 3 | 1 |
| 4 | 1 |
| 5 | 2 |
| 6 | 2 |
| 7 | 2 |
| 8 | 3 |
| 9 | 3 |
| 10 | 3 |

### 2. 使用 ``NTILE()`` 函数将行分配到 5 组：

```sql
SELECT ID,
NTILE (5) OVER (
ORDER BY ID
) Group_number
FROM geeks_demo; 
```

**输出:**

| ID | Group_number |
| --- | --- |
| 1 | 1 |
| 2 | 1 |
| 3 | 2 |
| 4 | 2 |
| 5 | 3 |
| 6 | 3 |
| 7 | 4 |
| 8 | 4 |
| 9 | 5 |
| 10 | 5 |

### 3. 如果尝试在没有 ``number_expression`` 的情况下使用 ``NTILE()`` 函数：

```sql
SELECT ID,
NTILE () OVER (
ORDER BY ID
) Group_number
FROM geeks_demo; 
```

**输出:**
会抛出以下错误:

```sql
The function 'NTILE' takes exactly 1 argument(s).
```