# 从 SQL Server 的表中提取邮件的域

> 原文: [https://www.geeksforgeeks.org/extract-domain-of-email-from-table-in-sql-server/](https://www.geeksforgeeks.org/extract-domain-of-email-from-table-in-sql-server/)

**简介**:
作为数据库管理员，您可能会遇到一个请求，您需要提取电子邮件地址的域，即存储在数据库表中的电子邮件地址。如果您想从任何给定的表中的电子邮件地址中统计最常用的域名，您可以统计从 SQL Server 的电子邮件中提取的域的数量，如下所示。

SQL 查询可用于从电子邮件地址中提取域。
让我们创建一个名为 `email_demo` 的表：

```sql
create table email_demo (ID int, Email varchar (200));
```

在表格 `email_demo` 中插入值：

```sql
insert into email_demo values
(1, 'Sam@gfg.com'), (2, 'Khushi@gfg.com'),
(3, 'Komal@gfg.org'), (4, 'Priya@xyz.com'),
(5, 'Sam@xyz.com'), (6, 'Krish@xyz.com'),
(7, 'Neha@gfg.com'), (8, 'Pam@gfg.com'),
(9, 'Mohan@abc.com'), (10, 'Ankit@mno.com'),
(11, 'Kumari@gfg.com'), (12, 'Hina@abc.com'),
(13, 'Jaya@mno.com'), (14, 'Piyush@abc.com'),
(15, 'Khushi@xyz.com'), (16, 'Mona@gfg.org'),
(17, 'Roza@abc.com');
```

显示表格内容：

```sql
select * from email_demo;
```

| ID | Email |
| --- | --- |
| 1 | Sam@gfg.com |
| 2 | Khushi@gfg.com |
| 3 | Komal@gfg.org |
| 4 | Priya@xyz.com |
| 5 | Sam@xyz.com |
| 6 | Krish@xyz.com |
| 7 | Neha@gfg.com |
| 8 | Pam@gfg.com |
| 9 | Mohan@abc.com |
| 10 | Ankit@mno.com |
| 11 | Kumari@gfg.com |
| 12 | Hina@abc.com |
| 13 | Jaya@mno.com |
| 14 | Piyush@abc.com |
| 15 | Khushi@xyz.com |
| 16 | Mona@gfg.org |
| 17 | Roza@abc.com |

## 1. 使用 SUBSTRING 函数提取域

在下面的例子中，我们将使用 [SUBSTRING 函数](https://www.geeksforgeeks.org/substring-function-in-sql-server/)来选择每个值中 `@` 符号之后的字符串。

**SQL 从电子邮件中提取域：**

```sql
SELECT ID,
SUBSTRING ([Email], CHARINDEX( '@', [Email]) + 1,
LEN([Email])) AS [Domain]
FROM [email_demo];
```

**输出：**

| ID | Domain |
| --- | --- |
| 1 | gfg.com |
| 2 | gfg.com |
| 3 | gfg.org |
| 4 | xyz.com |
| 5 | xyz.com |
| 6 | xyz.com |
| 7 | gfg.com |
| 8 | gfg.com |
| 9 | abc.com |
| 10 | mno.com |
| 11 | gfg.com |
| 12 | abc.com |
| 13 | mno.com |
| 14 | abc.com |
| 15 | xyz.com |
| 16 | gfg.org |
| 17 | abc.com |

**方法解析：**
*   这里，我们在 `SUBSTRING` 函数中将 Source 指定为我们的列名 `Email`。
*   接下来，我们使用 `CHARINDEX` 函数找到 `@` 符号，然后添加 1，这样起点就在 `@` 符号之后。
*   然后，我们使用 `LEN` 函数来指定结束值。

## 2. 在 SQL Server 中统计从电子邮件中提取的域名数量

### 方法 1
SQL 查询统计从电子邮件中提取域名的记录数量：

```sql
SELECT RIGHT ([Email],
LEN([Email]) - CHARINDEX( '@', [Email])) AS [Domain],
COUNT(*) AS [Total Number of Domain]
FROM [email_demo]
WHERE LEN([Email ]) > 0
GROUP BY RIGHT([Email],
LEN([Email]) - CHARINDEX( '@', [Email]));
```

**输出：**

| Domain | Total Number of Domain |
| --- | --- |
| abc.com | 4 |
| gfg.com | 5 |
| gfg.org | 2 |
| mno.com | 2 |
| xyz.com | 4 |

### 方法 2
统计从电子邮件中提取域名的记录数量的 SQL 查询：

```sql
SELECT SUBSTRING ([Email],
CHARINDEX( '@', [Email] ) + 1, LEN([Email])) AS [Domain],
COUNT(*) AS [Total Number of Domain]
FROM [email_demo]
WHERE LEN([Email]) > 1
GROUP BY SUBSTRING ([Email], CHARINDEX( '@', [Email] ) + 1,
LEN([Email]));
```

**输出：**

| Domain | Total Number of Domain |
| --- | --- |
| abc.com | 4 |
| gfg.com | 5 |
| gfg.org | 2 |
| mno.com | 2 |
| xyz.com | 4 |