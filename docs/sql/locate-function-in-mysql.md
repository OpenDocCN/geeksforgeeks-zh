# 在 MySQL 中定位()函数

> 原文:[https://www.geeksforgeeks.org/locate-function-in-mysql/](https://www.geeksforgeeks.org/locate-function-in-mysql/)

**LOCATE()** 函数在 MySQL 中用于查找字符串中某个子串的位置。它将返回字符串中第一个出现的子字符串的位置。如果字符串中不存在子字符串，则它将返回 0。当搜索字符串中子字符串的位置时，它不执行区分大小写的搜索。

**语法:**

```sql
LOCATE(substring, string, start)
```

**参数:**

此方法接受三个参数。

*   **子字符串–**
    要检索其位置的字符串。
*   **字符串–**
    要检索子字符串位置的字符串。
*   **开始–**
    搜索的开始位置。它是可选的。位置 1 是默认位置。

**返回:**
字符串中第一个出现的子字符串的位置。

**示例-1 :** 借助 LOCATE 函数在字符串“geeksforgeeks”中搜索字符串“f”。

```sql
SELECT LOCATE('f', 'geeksforgeeks') AS MatchLocation;
```

**输出:**

| MATCHLOCATION |
| --- |
| six |

**示例-2 :** 借助 LOCATE 函数在字符串“学习 SQL 很有趣”中搜索字符串“MYSQL”。所以，它将返回 0。

```sql
SELECT LOCATE('MYSQL', 'Learning SQL is fun') AS MatchLocation;
```

**输出:**

| MATCHLOCATION |
| --- |
| Zero |

**示例-3 :** 从位置 3 开始，借助 LOCATE 函数搜索字符串“geeksforgeeks”中的字符串“g”。

```sql
SELECT LOCATE('g', 'geeksforgeeks', 3) AS MatchLocation;
```

**输出:**

| MATCHLOCATION |
| --- |
| nine |

**示例-4 :**
LOCATE 函数也可以用于列数据。为了演示，创建一个名为 Student 的表。

```sql
CREATE TABLE Student
(
Student_id INT AUTO_INCREMENT,  
Student_name VARCHAR(100) NOT NULL,
Roll INT NOT NULL,
Department VARCHAR(10) NOT NULL,
PRIMARY KEY(Student_id )
);
```

向学生表中插入一些数据:

```sql
INSERT INTO Student
(Student_name, Roll, Department )
VALUES
('Anik Biswas ', 10100, 'CSE'),
('Bina Mallick', 11000, 'ECE' ),
('Aniket Sharma', 12000, 'IT' ),
('Sayani Samanta', 13000, 'ME'  ),
('Riyanka Shah ', 14000, 'EE' ),
('Bipin Kohli', 15000, 'CE' );
```

学生表如下。

```sql
SELECT  * from Student ;
```

| 学生标识 | 学生姓名 | 卷 | 部门 |
| --- | --- | --- | --- |
| one | 阿尼克·比斯瓦斯 | Ten thousand one hundred | 中学生毕业考试 |
| Two | 构建马利克 | Eleven thousand | 欧洲经济委员会 |
| three | 阿尼克·夏尔马 | Twelve thousand | 信息技术 |
| four | 萨尼·萨曼塔 | Thirteen thousand | 我 |
| five | 普里扬卡沙阿 | Fourteen thousand | 电子工程师 |
| six | 比平·科里 | Fifteen thousand | 这一个 |

现在，我们将在 LOCATE 函数的帮助下，在 Student_name 列中找到字符串“a”的第一次出现。

```sql
SELECT *, LOCATE('a', Student_name ) AS FirstOccurrenceOfA  
FROM STUDENT;
```

| 学生标识 | 学生姓名 | 卷 | 部门 | FirstOccurrenceOfA |
| --- | --- | --- | --- | --- |
| one | 阿尼克·比斯瓦斯 | Ten thousand one hundred | 中学生毕业考试 | one |
| Two | 构建马利克 | Eleven thousand | 欧洲经济委员会 | four |
| three | 阿尼克·夏尔马 | Twelve thousand | 信息技术 | one |
| four | 萨尼·萨曼塔 | Thirteen thousand | 我 | Two |
| five | 普里扬卡沙阿 | Fourteen thousand | 电子工程师 | four |
| six | 比平·科里 | Fifteen thousand | 这一个 | Zero |