# MySQL 中的 REPEAT()函数

> 原文:[https://www.geeksforgeeks.org/repeat-function-in-mysql/](https://www.geeksforgeeks.org/repeat-function-in-mysql/)

**REPEAT():**
MySQL 中的这个函数用于将一个字符串重复指定的次数。

**语法:**

```sql
REPEAT(str, count)
```

**参数:**
这个方法接受两个参数。

*   **字符串–**输入我们想要重复的字符串。
*   **计数–**它将描述重复字符串的次数。

**返回:**
返回一个重复的字符串。

**示例-1 :**
借助 REPEAT 函数重复字符串“极客”3 次。

```sql
SELECT REPEAT("Geeks", 3) 
AS Repeated_String;
```

**输出:**

| REPEATED_STRING |
| --- |
| 极客极客极客 |

**例-2 :**
借助 REPEAT 函数重复字符串‘SQL’0 次。

```sql
SELECT REPEAT("SQL", 0) 
AS Repeated_String;
```

**输出:**

| REPEATED_STRING |
| --- |
|   |

**例-3 :**
REPEAT 函数也可以用来重复列数据。为了演示，创建一个名为 Employee 的表。

```sql
CREATE TABLE Employee
(
Employee_id INT AUTO_INCREMENT,  
Employee_name VARCHAR(100) NOT NULL,
Joining_Date DATE NOT NULL,
PRIMARY KEY(Employee_id )
);
```

**在员工表中插入一些数据:**

```sql
INSERT INTO Employee
(Employee_name, Joining_Date )
VALUES
('Ananya ', '2000-01-11'),
('Anush ', '2002-11-10' ),
('Aniket ', '2005-06-11' ),
('Anika ', '2008-01-21'  ),
('Riyag ', '2008-02-01' ) ;
```

因此，员工表如下。

```sql
select * from Employee ;
```

**输出:**

| 员工标识 | 员工姓名 | 加入日期 |
| --- | --- | --- |
| one | Ananya |  2000-01-11 |
| Two | 阿努什 |  2002-11-10 |
| three | 阿尼克特 | 2005-06-11 |
| four | 夏嫣 | 2008-01-21 |
| five | Riyag | 2008-02-01 |

现在，我们将从 Employee_name 列中获取所有重复的字符串。

```sql
SELECT REPEAT(Employee_name, 2) 
AS Repeated_Name
FROM Employee;
```

**输出:**

| 重复名称 |
| --- |
| 阿纳尼亚 阿纳尼亚 |
| 阿努什阿努什 |
| 阿尼克特 阿尼克特 |
| 夏嫣·夏嫣 |
| Riyag Riyag |