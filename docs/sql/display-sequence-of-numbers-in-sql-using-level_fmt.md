# 使用级别

## 在 SQL 中显示数字序列

> 原文: [https://www.geeksforgeeks.org/display-sequence-of-numbers-in-sql-using-level/](https://www.geeksforgeeks.org/display-sequence-of-numbers-in-sql-using-level/)

术语 `LEVEL` 是指 Oracle 中的一个伪列，它在层次查询中用于以数字格式标识层次级别(父级->子级)。`LEVEL` 为根行返回 1，为根行的子行返回 2，以此类推，作为树状结构。`LEVEL` 必须与 `CONNECT BY` 子句一起使用。`CONNECT BY` 子句定义了层次结构的父行和子行之间的层次关系。`DUAL` 是 Oracle 数据库随数据字典自动生成的伪表。

### 示例-1

```sql
SELECT Level AS Sequence 
FROM Dual
CONNECT BY Level <= 5
```

**说明:**
上述查询将从 `dual` 执行初始值为 1 的 `Level`，这是伪表。“序列”充当 `别名`，即列的临时名称。在查询中，将检查条件，并在值为 1 的级别和指定条件之间使用“连接方式”创建关系。它将显示值，直到它通过指定的条件。

**输出:**

| 顺序 |
| :--- |
| 1 |
| 2 |
| 3 |
| 4 |
| 5 |

### 从特定的数字开始序列

`LEVEL` 可以帮助从任何特定的初始值开始一个数字序列。只需将比该值小一的值添加到“连接方式”中具有条件的 `LEVEL`。

**语法:**

```sql
SELECT Level+(n-1) AS Alias_Name
FROM Dual
CONNECT BY Level <= 10
```

其中 `n` 为初始具体数字，`Alias_Name` 为临时定义的列名。

### 示例-2

```sql
SELECT Level+(6-1) AS Sequence 
FROM Dual
CONNECT BY Level <= 10
```

**说明:**
用于显示 6 到 10 的数字序列。在上面的例子中，使用连接方式将小于 6 的 1 加到 `Level`，条件为 10。它将执行并显示指定值范围，作为虚拟表 `Dual` 中列名 `Sequence`。

**输出:**

| 顺序 |
| :--- |
| 6 |
| 7 |
| 8 |
| 9 |
| 10 |

### 示例-3

```sql
SELECT Level AS Sequence, Sysdate AS System_date 
FROM Dual
CONNECT BY Level <= 5
```

**说明:**
上述查询将执行并显示数字序列和日期。`Level` 具有临时列名 `Sequence`，`Sysdate` 具有列名 `System_date`，如定义的那样。它将从名为 `Dual` 的虚拟表中检索数据。根据“连接方式”中指定的条件，它将有 5 个行数，从 `Sequence` 列中的 1 到 5，并且在 `System_date` 列中的所有 5 行中都有相同的日期。

**输出:**

| 顺序 | 系统日期 |
| :--- | :--- |
| 1 | 2019-01-05 |
| 2 | 2019-01-05 |
| 3 | 2019-01-05 |
| 4 | 2019-01-05 |
| 5 | 2019-01-05 |