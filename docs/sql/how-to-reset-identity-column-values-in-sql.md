# 如何在 SQL 中重置标识列值

> 原文:[https://www . geesforgeks . org/如何重置-identity-column-values-in-SQL/](https://www.geeksforgeeks.org/how-to-reset-identity-column-values-in-sql/)

### 什么是“身份栏”？

表的标识列是其值自动增加的列。用户通常不能在标识列中插入值。一个表只能有一个用 identity 属性定义的列。

**语法:**

```sql
IDENTITY [ ( seed , increment ) ]
```

身份的默认值是身份(1，1)。

**种子:**种子代表一个 ID 的起始值，种子的默认值为 1。

**增量:**表示 ID 的增量值，增量默认值为 1。

**例如:**

**第一步:**创建一个名为学校的表。

```sql
CREATE TABLE school (
student_id INT IDENTITY,
student_name VARCHAR(200),
marks INT
);
```

这里，表中的“student_id”列从 1 开始，因为 seed 的默认值是 1，每行递增 1。

**步骤 2 :** 在表格中插入一些值。

```sql
INSERT INTO school (student_name, marks) VALUES ('Sahil', 100);
INSERT INTO school (student_name, marks) VALUES ('Raj', 78);
INSERT INTO school (student_name, marks) VALUES ('Navneet', 80);
INSERT INTO school (student_name, marks) VALUES ('Rahul', 75);
INSERT INTO school (student_name, marks) VALUES ('Sudeep', 82);
INSERT INTO school (student_name, marks) VALUES ('Azaan', 75);
```

**第三步:**要查看‘学校’表中的记录，我们可以使用以下代码:

```sql
SELECT * FROM school;
```

**输出:**

<figure class="table">

|  | [Student id] | [Student name] | [mark] |
| --- | --- | --- | --- |
| one |

</figure>

**步骤 4 :** 让我们删除一条记录。

```sql
DELETE FROM school WHERE student_id = 4;
```

**第五步:**查看表格中的记录。

```sql
SELECT * FROM school;
```

**输出:**

<figure class="table">

|  | [Student id] | [Student name] | [mark] |
| --- | --- | --- | --- |
| one |

</figure>

现在，您可以看到 student_id 列没有按顺序排列，因此您必须重置 Identity 列。

### 使用 DBCC 校验识别方法重置身份值:

这里，要在 SQL Server 中重置标识列，可以使用 DBCC 检查标识方法。

**语法:**

```sql
DBCC CHECKIDENT ('table_name', RESEED, new_value);
```

**注意:**如果我们重置表中已有的记录，插入新的记录，那么会显示错误。

所以，我们需要:

*   Create a new table as a backup of the main table (i.e. school).
*   Delete all data from the main table.
*   Now reset the identity bar.
*   Re-insert all data in the backup table into the main table.

**步骤 6 :** 创建名为“new_school”的备份表。

```sql
CREATE TABLE new_school AS SELECT student_id, student_name, marks FROM school;
```

**第七步:**删除学校所有数据。

```sql
DELETE FROM school;
```

**第 8 步:**重置身份列。

```sql
DBCC CHECKIDENT ('school', RESEED, 0);
```

**步骤 9 :** 将备份表中的所有数据重新插入主表。

```sql
INSERT INTO school (student_name, marks) SELECT student_name, marks FROM new_school ORDER BY student_id ASC;
```

**第十步:**见表中记载。

```sql
SELECT * FROM school;
```

**输出:**

<figure class="table">

|  | [Student id] | [Student name] | [mark] |
| --- | --- | --- | --- |
| one |

</figure>

这是在 SQL 中重置标识列值的方法。