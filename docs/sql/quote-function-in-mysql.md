# MySQL 中的 QUOTE()函数

> 原文:[https://www.geeksforgeeks.org/quote-function-in-mysql/](https://www.geeksforgeeks.org/quote-function-in-mysql/)

**QUOTE():**
MySQL 中的这个函数用来返回一个结果，这个结果可以作为 SQL 语句中一个正确转义的数据值。返回的字符串用单引号括起来，反斜杠(\)、单引号(')、ASCII 空值和 Control+Z 的每个实例前面都有反斜杠。如果参数为空，返回值为单词“空”，不包含单引号。

**语法:**

```sql
QUOTE(string)
```

**参数:**
此方法接受一个参数。

*   **字符串–**输入字符串。

**返回:**
它在一条 SQL 语句中返回一个带有正确转义数据值的字符串。

**示例-1 :**
借助 QUOTE 函数将字符串“极客”中的单引号转义为“极客”。

```sql
SELECT QUOTE('geeks''for''geeks' ) 
AS Escaped_String;
```

**输出:**

| 转义字符串 |
| --- |
| “极客”代表“极客” |

**示例-2 :**
借助 QUOTE 函数对字符串 geeks \ for ' \ geeks '中的反斜杠进行转义。

```sql
SELECT QUOTE('geeks\for\geeks' ) 
AS Escaped_String;
```

**输出:**

| 转义字符串 |
| --- |
| 极客们 |

**例-3 :**
QUOTE 函数也可以用于列数据。为了演示，创建一个名为 Student 的表。

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

**在学生表中插入一些数据:**

```sql
INSERT INTO Student
(Student_name, Roll, Department )
VALUES
('Anik Biswas ', 10100, 'CSE'),
('Bina Mallick', 11000, 'ECE' ),
('Aniket Sharma', 12000, 'IT' ),
('Sayani Samanta', 13000, 'ME'  ),
('Riyanka Shah ', 14000, 'EE' ) ;
```

学生表如下。

```sql
SELECT  * from Student ;

```

**输出:**

| 学生标识 | 学生姓名 | 卷 | 部门 |
| --- | --- | --- | --- |
| one | 阿尼克·比斯瓦斯 | Ten thousand one hundred | 中学生毕业考试 |
| Two | 构建马利克 | Eleven thousand | 欧洲经济委员会 |
| three | 阿尼克·夏尔马 | Twelve thousand | 信息技术 |
| four | 萨尼·萨曼塔 | Thirteen thousand | 我 |
| five | 普里扬卡沙阿 | Fourteen thousand | 电子工程师 |

现在，我们将在部门列中使用报价功能。

```sql
SELECT *, QUOTE (Department) FROM Student;
```

**输出:**

| 学生标识 | 学生姓名 | 卷 | 部门 | 报价(部门) |
| --- | --- | --- | --- | --- |
| one | 阿尼克·比斯瓦斯 | Ten thousand one hundred | 中学生毕业考试 | ' CSE ' |
| Two | 构建马利克 | Eleven thousand | 欧洲经济委员会 | 欧洲经委会 |
| three | 阿尼克·夏尔马 | Twelve thousand | 信息技术 | 信息技术 |
| four | 萨尼·萨曼塔 | Thirteen thousand | 我 | 我 |
| five | 普里扬卡沙阿 | Fourteen thousand | 电子工程师 | ' EE ' |