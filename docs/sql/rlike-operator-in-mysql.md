# MySQL 中的 RLIKE 操作符

> 原文:[https://www.geeksforgeeks.org/rlike-operator-in-mysql/](https://www.geeksforgeeks.org/rlike-operator-in-mysql/)

**RLIKE :**
这个操作符在 [MySQL](https://www.geeksforgeeks.org/mysql-common-mysql-queries/) 中用于执行字符串表达式与模式的模式匹配。

**语法:**

```sql
RLIKE pattern

```

**参数:**
这个方法接受语法中提到的一个参数。

*   **模式–**我们想要与表达式匹配的模式。下面描述了各种模式及其用法。

| **图案** | **模式匹配什么** |
| --- | --- |
| * | 它前面零个或多个字符串实例 |
| + | 它前面的一个或多个字符串实例 |
| 。 | 任何单个字符 |
| ？ | 匹配前面字符串的零个或一个实例。 |
| ^ | caret(^)匹配字符串的开头 |
| $ | 字符串结尾 |
| [abc] | 方括号中列出的任何字符 |
| [^abc] | 方括号中未列出的任何字符 |
| [阿-兹] | 匹配任何大写字母。 |
| [a-z] | 匹配任何小写字母 |
| [0-9] | 匹配从 0 到 9 的任何数字。 |
| [[:<:/> | 匹配单词的开头。 |
| [[:>:]] | 匹配单词的结尾。 |
| [:类:] | 匹配字符类，即[:alpha:]匹配字母，[:space:]匹配空格，[:pi 点:]是匹配标点符号，而[:upper:]是匹配大写字母。 |
| p1&#124;p2&#124;p3 | 交替；匹配任何模式 p1、p2 或 p3 |
| {n} | 前面元素的 n 个实例 |
| {m，n} | 前面元素的 m 到 n 个实例 |

**示例-1 :**
以下示例查找姓氏以字母 s 开头的员工

```sql
CREATE TABLE Employee
(
Employee_id INT AUTO_INCREMENT,  
First_name VARCHAR(100) NOT NULL,
Last_name VARCHAR(100) NOT NULL,
Joining_Date DATE NOT NULL,
PRIMARY KEY(Employee_id )
);
```

**在员工表中插入一些数据:**

```sql
INSERT INTO Employee
(First_name ,Last_name , Joining_Date )
VALUES
('Sayantan', 'Majumdar', '2000-01-11'),
('Anushka', 'Samanta', '2002-11-10' ),
('Sayan', 'Sharma', '2005-06-11' ),
('Shayari', 'Das', '2008-01-21' ),
('Sayani', 'Jain', '2008-02-01' ),
('Tapan', 'Samanta', '2010-01-11' ),
('Deepak', 'Sharma', '2014-12-01'  ),
('Ankana', 'Jana', '2018-08-17'),
('Shreya', 'Ghosh', '2020-09-10') ;
```

因此，员工表如下。

```sql
select * from Employee ;
```

**输出:**

| 员工 id | 名字 | 姓氏 | 加入日期 |
| --- | --- | --- | --- |
| one | 萨彦坦 | Majumdar | 2000-01-11 |
| Two | 阿努什卡 | 萨曼塔 | 2002-11-10 |
| three | Sayan | 夏尔马 | 2005-06-11 |
| four | 沙雅里 | 这是什么 | 2008-01-21  |
| five | Sayani | 耆那教教徒 | 2008-02-01 |
| six | 塔潘 | 萨曼塔 | 2010-01-11 |
| seven | 迪帕克（男子名） | 夏尔马 | 2014-12-01 |
| eight | 安卡拉 | 陈娟儿 | 2018-08-17 |
| nine | 施莱 | 幽灵 | 2020-09-10  |

现在，我们将检查那些姓氏带有“S”的员工。

```sql
SELECT * FROM Employee   
WHERE Last_name RLIKE '^S' ;
```

**输出:**

| 员工 id | 名字 | 姓氏 | 加入日期 |
| --- | --- | --- | --- |
| Two | 阿努什卡 | 萨曼塔 | 2002-11-10 |
| three | Sayan | 夏尔马 | 2005-06-11 |
| six | 塔潘 | 萨曼塔 | 2010-01-11 |
| seven | 迪帕克（男子名） | 夏尔马 | 2014-12-01  |

**示例-2 :**
以下示例查找名字以字母“I”结尾的员工。

```sql
SELECT * FROM Employee   
WHERE First_name RLIKE 'i{content}apos; ;
```

**输出:**

| 员工 id | 名字 | 姓氏 | 加入日期 |
| --- | --- | --- | --- |
| four | 沙雅里 | 这是什么 | 2008-01-21 |
| five | Sayani | 耆那教教徒 | 2008-02-01 |