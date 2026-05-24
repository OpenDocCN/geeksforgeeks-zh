# 删除 MS SQL Server 中的重复项

> 原文:[https://www . geesforgeks . org/delete-duplicates-in-ms-SQL-server/](https://www.geeksforgeeks.org/delete-duplicates-in-ms-sql-server/)

任何表中的重复值都可能是由于不良的表设计或其他来源的不需要的数据造成的。要从 SQL Server 中的表中删除重复数据，请执行以下步骤–

1.  查找重复的行。
2.  使用 DELETE 语句删除重复的行。

让我们创建一个名为 Geek–

```sql
CREATE TABLE Geek(
Name NVARCHAR(100) NOT NULL,
Email NVARCHAR(255) NOT NULL,
City NVARCHAR(100) NOT NULL);
```

让我们在表 Geek 中插入一些值–

```sql
INSERT INTO Geek (Name, Email, City) VALUES
('Nisha', 'nisha@gfg.com', 'Delhi'),
('Megha', 'megha@gfg.com', 'Noida'),
('Khushi', 'khushi@gfg.com', 'Jaipur'),
('Khushi', 'khushi@gfg.com', 'Jaipur'),
('Khushi', 'khushi@gfg.com', 'Jaipur'),
('Hina', 'hina@gfg.com', 'Kanpur'),
('Hina', 'hina@gfg.com', 'Kanpur'),
('Misha', 'misha@gfg.com', 'Gurugram'),
('Misha', 'misha@gfg.com', 'Gurugram'),
('Neha', 'neha@gfg.com', 'Pilani');
```

让我们显示一下 Geek 表的内容–

```sql
SELECT * 
FROM Geek;
```

**表–**极客

| 名字 | 电子邮件 | 城市 |
| --- | --- | --- |
| 妮莎 | nisha@gfg.com | 德里 |
| 非常 | megha@gfg.com | 无聊死了 |
| 库希 | khushi@gfg.com(中文) | 斋浦尔 |
| 库希 | khushi@gfg.com(中文) | 斋浦尔 |
| 库希 | khushi@gfg.com(中文) | 斋浦尔 |
| 希娜 | hina@gfg.com(中文) | 坎普尔。原称 CAWNPORE |
| 希娜 | hina@gfg.com(中文) | 坎普尔。原称 CAWNPORE |
| 希娜 | hina@gfg.com(中文) | 坎普尔。原称 CAWNPORE |
| 米沙 | 米沙@gfg.com | 我很自豪 |
| 米沙 | 米沙@gfg.com | 我很自豪 |
| 停止 | neha@gfg.com | 皮拉尼 |

**SQL Server 查询从表 Geek 中删除重复记录:**

```sql
WITH CTE AS (
SELECT Name, Email, City
ROW_NUMBER() OVER (
PARTITION BY Name, Email. City
ORDER BY Name, Email. City
) row_num
FROM Geek
)
DELETE FROM CTE
WHERE row_num > 1;
```

**输出–**
(受影响 5 行)

```sql
SELECT * 
FROM Geek;
```

**表–**极客

| 名字 | 电子邮件 | 城市 |
| --- | --- | --- |
| 妮莎 | nisha@gfg.com | 德里 |
| 非常 | megha@gfg.com | 无聊死了 |
| 库希 | khushi@gfg.com(中文) | 斋浦尔 |
| 希娜 | hina@gfg.com(中文) | 坎普尔。原称 CAWNPORE |
| 米沙 | 米沙@gfg.com | 我很自豪 |
| 停止 | neha@gfg.com | 皮拉尼 |