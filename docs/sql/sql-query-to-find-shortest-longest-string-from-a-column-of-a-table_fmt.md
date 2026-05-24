# 从表的一列中找到最短的&最长的字符串的 SQL 查询

> 原文：[https://www.geeksforgeeks.org/sql-query-to-find-shortest-longest-string-from-a-column-of-a-table/](https://www.geeksforgeeks.org/sql-query-to-find-shortest-longest-string-from-a-column-of-a-table/)

在这里，我们将看到如何在 SQL 查询的帮助下从数据库中的一个表的一列中找到最短和最长的字符串。我们将首先创建一个数据库 `geeks`，然后我们创建一个表 `friends` 与 `firstName`、`lastName`、`age` 列。然后将对该表执行我们的 SQL 查询，以检索列中最短和最长的字符串。

在本文中，我们将使用微软的 SQL Server 作为我们的数据库。

### 创建数据库：

使用下面的 SQL 语句创建一个名为 `geeks` 的数据库：

```sql
CREATE DATABASE geeks;
```

### 使用数据库：

```sql
USE geeks;
```

### 表格定义：

我们的 `geeks` 数据库中有以下员工表：

```sql
CREATE TABLE friends(
firstName VARCHAR(30) not NULL,
lastName VARCHAR(30) not NULL,
age INT NOT NULL);
```

您可以使用下面的语句来查询创建的表的描述：

```sql
EXEC SP_COLUMNS friends;
```

![](img/b67458066065cee5a3e871b38c14d502.png)

### 向表中添加数据：

使用以下语句向 `friends` 表添加数据：

```sql
INSERT INTO friends
values
('Ajit','Yadav', 20),
('Ajay', 'More', 21),
('Amir', 'Jawadwala', 21),
('Zara', 'Khan', 20),
('Yogesh', 'Vaishnav', 21),
('Ashish', 'Yadav', 21),
('Govind', 'Vaishnav', 22),
('Vishal', 'Vishwakarma', 21);
```

要验证表格的内容，请使用以下语句：

```sql
SELECT * FROM friends;
```

![](img/823168e93e242d356a203012b2d063db.png)

现在让我们使用 `char_length()`、`min()` 和 `max()` 函数和 `LIMIT` 子句，从刚刚创建的表中找到最短和最长的 `firstName`。

### 最短的 `firstName`：

使用如下语法在 `friends` 表中找到最短的 `firstName`：

> **语法：**
>
> `SELECT TOP 1 * FROM <table_name>` – 这里我们只想要一行，这就是为什么 `TOP 1 *`
>
> `WHERE`
>
> `len( <string_column>) =`
>
> `(SELECT min(len(<string_column>)) FROM <table_name>);`

**示例：**

```sql
SELECT TOP 1 * FROM friends
WHERE
len(firstName) = 
(SELECT min(len(firstName)) FROM friends);
```

**输出：**

![](img/e9d469340d08daac9256d589f9a1db7a.png)

### 排在词典上最短的 `firstName`：

如果有多个具有相同最小长度的字符串，并且我们想要按照字典顺序检索最短的字符串，则可以执行以下操作：

> **语法：**
>
> `SELECT TOP 1 * FROM <table_name>` – 这里我们只需要一行，这就是为什么 `TOP 1 *`。
>
> `WHERE`
>
> `len( <string_column>) =`
>
> `(SELECT min(len(<string_column>)) FROM <table_name>)`
>
> `ORDER BY <column_name>;` – 在这种情况下，列名将是 `firstName`。

**示例：**

```sql
SELECT TOP 1 *  FROM friends
WHERE
len(firstName) = 
(SELECT min(len(firstName)) FROM friends)
ORDER BY firstname;
```

**输出：**

![](img/4284088ecda31f16b77e9f37cbcc0030.png)

### 最长的一排 `firstName`：

> **语法：**
>
> `SELECT TOP 1 * FROM <table_name>`
>
> `WHERE`
>
> `len( <string_column>) =`
>
> `(SELECT max(len(<string_column>)) FROM <table_name>);`

**示例：**

```sql
SELECT TOP 1 * FROM friends
WHERE
len(firstName) = 
(SELECT max(len(firstName)) FROM friends);
```

**输出：**

![](img/8b555e6c4c0eabe614094e5a7bc8359a.png)

### 排在词典上最长的 `firstName`：

> **语法：**
>
> `SELECT TOP 1 * FROM <table_name>`
>
> `WHERE`
>
> `len( <string_column>) =`
>
> `(SELECT max(len(<string_column>)) FROM <table_name>)`
>
> `ORDER BY <string_column>;` – 在这里，我们将按 `firstName` 排序数据。

**示例：**

```sql
SELECT TOP 1* FROM friends
WHERE
len(firstName) = 
(SELECT max(len(firstName)) FROM friends) 
ORDER BY firstName;
```

**输出：**

![](img/159ebda9beac0fdd76cb3ea439f67465.png)