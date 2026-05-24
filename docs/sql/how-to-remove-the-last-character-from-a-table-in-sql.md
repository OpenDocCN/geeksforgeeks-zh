# 如何删除 SQL 中表的最后一个字符？

> 原文:[https://www . geesforgeks . org/如何从 sql 中的表中删除最后一个字符/](https://www.geeksforgeeks.org/how-to-remove-the-last-character-from-a-table-in-sql/)

在这里，我们将看到，如何删除 SQL 表中的最后一个字符。我们可以使用 SUBSTRING()函数来完成这个任务。

**SUBSTRING():** 这个函数用来从给定的位置找到给定字符串的一部分。它需要三个参数:

*   字符串:这是必需的参数。它是要应用函数的字符串。
*   开始:它给出了字符串的开始位置。它也是必需的参数。
*   长度:这是一个可选参数。默认情况下，它采用要返回的子字符串的长度。

**查询:**

```sql
SELECT SUBSTRING('HELLO GEEKS', 1, 5);
```

![](img/6e720625008ab9221d28c0497a091fd7.png)

**输出:**

![](img/59b6fe1d02d84359dad6e15f0c447b02.png)

要从字段中删除最后一个字符，请传递长度参数，使其比总长度小 1。

出于演示的目的，让我们在名为“极客”的数据库中创建一个 demo_table。

**步骤 1:** 创建数据库

使用下面的 SQL 语句创建一个名为 geeks 的数据库。

**查询:**

```sql
CREATE DATABASE geeks;
```

**步骤 2:** 使用数据库

使用下面的 SQL 语句将数据库上下文切换到极客。

**查询:**

```sql
USE geeks;
```

**步骤 3:** 表格定义

我们的极客数据库中有以下演示表。

**查询:**

```sql
 CREATE TABLE demo_table
(FIRSTNAME VARCHAR(20),
LASTNAME VARCHAR(20),
AGE INT);
```

**第 4 步:**插入数据

**查询:**

```sql
INSERT INTO demo_table VALUES
('Romy', 'Kumari', 22 ),
('Pushkar', 'Jha', 23),  
('Meenakshi', 'Jha', 20),
('Shalini', 'Jha', 22),
('Nikhil', 'Kalra', 23),
('Akanksha', 'Gupta', 23);
```

**第五步:**查看内容

**查询:**

```sql
SELECT * FROM demo_table;
```

**输出:**

![](img/da721029b8453c83a9231bd4acb4a761.png)

**第 6 步:**SUBSTRING()函数的使用

*   我们将删除 LASTNAME 列中条目的最后一个字符。

**语法:**

```sql
SELECT SUBSTRING(column_name,1,LEN(column_name)-1) 
FROM table_name;
```

**查询:**

```sql
SELECT FIRSTNAME, SUBSTRING(LASTNAME,1,LEN(LASTNAME)-1)
 AS LASTNAME, AGE FROM demo_table;
```

![](img/3f7d779a1ed4df7ef92f4cf2b1a252db.png)

**输出:**

![](img/c06a1081e70703e6e7de1cc4300c5716.png)

我们可以在图像中看到，LASTNAME 列中的最后一个字符现在被删除了。

*   我们将删除“名字”列中条目的最后一个字符。

**查询:**

```sql
SELECT SUBSTRING(FIRSTNAME,1,LEN(FIRSTNAME)-1)
 AS FIRSTNAME, LASTNAME, AGE FROM demo_table;
```

![](img/6f9d74ecd70d9e8d8a43c0e649088a54.png)

**输出:**

![](img/47b291cdcd6e201e8c68365e9ef9eca1.png)