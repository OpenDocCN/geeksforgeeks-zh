# SQL INSERT 语句

> 原文: [https://www.geeksforgeeks.org/sql-insert-statement/](https://www.geeksforgeeks.org/sql-insert-statement/)

SQL 的 `INSERT INTO` 语句用于在表中插入一个新行。使用 `INSERT INTO` 语句插入行有两种方式：

## 1. 仅值

第一种方法是只指定要插入的数据的值，而不指定列名。

> `INSERT INTO table_name VALUES(value1, value2, value3, ...);`
> - `table_name`: 表的名称
> - `value1`, `value2`, ...: 新记录的第一列、第二列、…的值

## 2. 列名和值两者

在第二种方法中，我们将指定要填充的列及其对应的值，如下所示：

> `INSERT INTO table_name(column1, column2, column3, ...) VALUES(value1, value2, value3, ...);`
> - `table_name`: 表的名称
> - `column1`, `column2`, ...: 第一列、第二列的名称……
> - `value1`, `value2`, `value3`: 新记录的第一列、第二列的值……

[![table1](img/4fab6fceee0b1d1b256c3430eb713844.png)](https://media.geeksforgeeks.org/wp-content/cdn-uploads/table11.jpg)

## 查询

### 方法 1 (仅插入值)

> `INSERT INTO STUDENT VALUES('5', 'SHYAM', 'WEST BENGAL', 'XXXXXXXXXX', '19');`

**输出：**
表格 `STUDENT` 现在看起来像：

| **ROLL_NO** | **NAME** | **ADDRESS** | **PHONE** | **AGE** |
| --- | --- | --- | --- | --- |
| 1 | RAM | DELHI | XXXXXXXXXX | 18 |
| 2 | RAMESH | GURGAON | XXXXXXXXXX | 18 |
| 3 | SUJIT | ROHTAK | XXXXXXXXXX | 20 |
| 4 | SURESH | DELHI | XXXXXXXXXX | 18 |
| 3 | SUJIT | ROHTAK | XXXXXXXXXX | 20 |
| 2 | RAMESH | GURGAON | XXXXXXXXXX | 18 |
| 5 | SHYAM | WEST BENGAL | XXXXXXXXXX | 19 |

### 方法 2 (仅在指定的列中插入值)

> `INSERT INTO STUDENT(ROLL_NO, NAME, AGE) VALUES('5', 'PRATIK', '19');`

**输出：**
表格 `STUDENT` 现在看起来像：

| **ROLL_NO** | **NAME** | **ADDRESS** | **PHONE** | **AGE** |
| --- | --- | --- | --- | --- |
| 1 | RAM | DELHI | XXXXXXXXXX | 18 |
| 2 | RAMESH | GURGAON | XXXXXXXXXX | 18 |
| 3 | SUJIT | ROHTAK | XXXXXXXXXX | 20 |
| 4 | SURESH | DELHI | XXXXXXXXXX | 18 |
| 3 | SUJIT | ROHTAK | XXXXXXXXXX | 20 |
| 2 | RAMESH | GURGAON | XXXXXXXXXX | 18 |
| 5 | PRATIK | null | null | 19 |

请注意，未提供值的列由 `null` 填充。这是这些列的默认值。

## 在插入语句中使用选择

我们可以使用 `SELECT` 语句和 `INSERT INTO` 语句从一个表中复制行，然后将它们插入另一个表中。该语句的用法类似于 `INSERT INTO` 语句。不同之处在于，这里使用 `SELECT` 语句从不同的表中选择数据。使用 `INSERT...SELECT` 语句的不同方式如下所示：

### 插入表的所有列

我们可以复制一个表的所有数据并插入到另一个不同的表中。

> `INSERT INTO first_table SELECT * FROM second_table;`
> - `first_table`: 首表名称。
> - `second_table`: 秒表名称。

我们使用 `SELECT` 语句从一个表中复制数据，并使用 `INSERT INTO` 语句插入到另一个表中。

### 插入表的特定列

我们可以只复制一个表中我们想要插入到另一个不同表中的那些列。

**语法：**

> `INSERT INTO first_table(name_of_columns1) SELECT name_of_columns2 FROM second_table;`
> - `first_table`: 首表名称。
> - `second_table`: 秒表名称。
> - `name_of_columns1`: 表 1 中用逗号 (`,`) 分隔的列名。
> - `name_of_columns2`: 表 2 中用逗号 (`,`) 分隔的列名。

我们使用 `SELECT` 语句只从第二个表中复制选定列的数据，使用 `INSERT INTO` 语句插入第一个表。

### 从表中复制特定行

我们可以通过 `SELECT` 语句使用 `WHERE` 子句从一个表中复制特定行插入到另一个表中。我们必须在 `WHERE` 子句中提供适当的条件来选择特定的行。

> `INSERT INTO table1 SELECT * FROM table2 WHERE condition;`
> - `first_table`: 首表名称
> - `second_table`: 秒表名称
> - `condition`: 条件选择具体行

**表 2: LateralStudent**

| **ROLL_NO** | **NAME** | **ADDRESS** | **PHONE** | **AGE** |
| --- | --- | --- | --- | --- |
| 7 | VIJAY | DAMAN | XXXXXXXXXX | 18 |
| 8 | NIRAJ | BAREILLY | XXXXXXXXXX | 19 |
| 9 | SOMESH | ROHTAK | XXXXXXXXXX | 20 |

### 查询

#### 方法 1 (插入所有行和列)

> `INSERT INTO STUDENT SELECT * FROM LateralStudent;`

**输出：**
该查询会将 `LateralStudent` 表的所有数据插入到 `STUDENT` 表中。`STUDENT` 表现在看起来像：

| **ROLL_NO** | **NAME** | **ADDRESS** | **PHONE** | **AGE** |
| --- | --- | --- | --- | --- |
| 1 | RAM | DELHI | XXXXXXXXXX | 18 |
| 2 | RAMESH | GURGAON | XXXXXXXXXX | 18 |
| 3 | SUJIT | ROHTAK | XXXXXXXXXX | 20 |
| 4 | SURESH | DELHI | XXXXXXXXXX | 18 |
| 3 | SUJIT | ROHTAK | XXXXXXXXXX | 20 |
| 2 | RAMESH | GURGAON | XXXXXXXXXX | 18 |
| 7 | VIJAY | DAMAN | XXXXXXXXXX | 18 |
| 8 | NIRAJ | BAREILLY | XXXXXXXXXX | 19 |
| 9 | SOMESH | ROHTAK | XXXXXXXXXX | 20 |

#### 方法 2 (插入特定列)

> `INSERT INTO STUDENT(ROLL_NO, NAME, AGE) SELECT ROLL_NO, NAME, AGE FROM LateralStudent;`

**输出：**
该查询会将 `LateralStudent` 表的 `ROLL_NO`、`NAME` 和 `Age` 列中的数据插入到 `STUDENT` 表中，`STUDENT` 表中的其余列将由 `null` 填充，这是其余列的默认值。`STUDENT` 表现在看起来像：

| **ROLL_NO** | **NAME** | **ADDRESS** | **PHONE** | **AGE** |
| --- | --- | --- | --- | --- |
| 1 | RAM | DELHI | XXXXXXXXXX | 18 |
| 2 | RAMESH | GURGAON | XXXXXXXXXX | 18 |
| 3 | SUJIT | ROHTAK | XXXXXXXXXX | 20 |
| 4 | SURESH | DELHI | XXXXXXXXXX | 18 |
| 3 | SUJIT | ROHTAK | XXXXXXXXXX | 20 |
| 2 | RAMESH | GURGAON | XXXXXXXXXX | 18 |
| 7 | VIJAY | null | null | 18 |
| 8 | NIRAJ | null | null | 19 |
| 9 | SOMESH | null | null | 20 |

#### 选择特定行插入

> `INSERT INTO STUDENT SELECT * FROM LateralStudent WHERE AGE = 18;`

**输出：**
该查询将只选择表格 `LateralStudent` 中的第一行插入 `STUDENT` 表格。`STUDENT` 表现在看起来像：

| **ROLL_NO** | **NAME** | **ADDRESS** | **PHONE** | **AGE** |
| --- | --- | --- | --- | --- |
| 1 | RAM | DELHI | XXXXXXXXXX | 18 |
| 2 | RAMESH | GURGAON | XXXXXXXXXX | 18 |
| 3 | SUJIT | ROHTAK | XXXXXXXXXX | 20 |
| 4 | SURESH | DELHI | XXXXXXXXXX | 18 |
| 3 | SUJIT | ROHTAK | XXXXXXXXXX | 20 |
| 2 | RAMESH | GURGAON | XXXXXXXXXX | 18 |
| 7 | VIJAY | DAMAN | XXXXXXXXXX | 18 |

## 使用单个 SQL 语句向表中插入多行

```sql
INSERT INTO table_name(Column1, Column2, Column3, .......) 
VALUES (Value1, Value2, Value3, .....),
       (Value1, Value2, Value3, .....),
       (Value1, Value2, Value3, .....),
       ............................. ;
```
- `table_name`: 表的名称
- `Column1`: 第一列、第二列……的名称
- `Value1`, `Value2`, `Value3`: 为每个新插入行的第一列、第二列……提供的值

你需要提供多个值列表，每个列表用 `,` 分隔。每个值列表对应于要插入表中每个新行的值。下一个列表中的值告诉要插入表中下一行的值。

### 示例

以下 SQL 语句在 `STUDENT` 表中插入多行。

```sql
INSERT INTO STUDENT(ID, NAME, AGE, GRADE, CITY) 
VALUES(1, "AMIT KUMAR", 15, 10, "DELHI"),
      (2, "GAURI RAO", 18, 12, "BANGALORE"),
      (3, "MANAV BHATT", 17, 11, "NEW DELHI"),
      (4, "RIYA KAPOOR", 10, 5, "UDAIPUR");
```

**输出：`STUDENT` 表**
该查询将在 `STUDENT` 表的每一连续行中插入所有值。因此，`STUDENT` 表将如下所示：

| **ID** | **NAME** | **AGE** | **GRADE** | **CITY** |
| --- | --- | --- | --- | --- |
| 1 | AMIT KUMAR | 15 | 10 | DELHI |
| 2 | GAURI RAO | 18 | 12 | BANGALORE |
| 3 | MANAV BHATT | 17 | 11 | NEW DELHI |
| 4 | RIYA KAPOOR | 10 | 5 | UDAIPUR |

本文由 [**Harsh Agarwal**](https://www.facebook.com/harsh.agarwal.16752) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 `contribute@geeksforgeeks.org`。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。