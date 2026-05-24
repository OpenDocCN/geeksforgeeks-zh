# MySQL 中的 CONCAT()函数

> 原文:[https://www.geeksforgeeks.org/concat-function-in-mysql/](https://www.geeksforgeeks.org/concat-function-in-mysql/)

**MySQL 中的 CONCAT()** 函数用于连接给定的参数。它可能有一个或多个参数。如果所有参数都是非二进制字符串，则结果是非二进制字符串。如果参数包含任何二进制字符串，则结果为二进制字符串。如果给定了一个数字参数，那么它将被转换为等效的非二进制字符串形式。

**语法:**

```sql
CONCAT(str1, str2, ...)

```

**参数:**该方法接受 N 个参数。

*   **str1，str2.str3…:**我们想要连接的输入信号。

**返回:**串联所有输入字符串后返回一个新字符串。如果任何输入字符串为空，则返回空值。

**示例-1 :**
使用 CONCAT 函数连接 3 个字符串。

```sql
SELECT CONCAT('geeks', 'for', 'geeks') AS ConcatenatedString ;

```

**输出:**

| 串联数据环 |
| --- |
| 极客们 |

**示例-2 :**
使用 CONCAT 函数连接数字字符串。

```sql
SELECT CONCAT(19, 10, 5.60) AS ConcatenatedNumber ;

```

**输出:**

| 串联数字 |
| --- |
| Nineteen thousand one hundred and five point six |

**示例-3 :**
使用 CONCAT 函数连接包含空字符串的字符串。

```sql
SELECT CONCAT('geeks', 'for', 'geeks', NULL) AS ConcatenatedString ;

```

**输出:**

| 串联数据环 |
| --- |
| 空 |

**示例-4 :**
在本例中，我们将在表的列之间连接字符串。为了演示，创建一个名为 Student 的表。

```sql
CREATE TABLE Student(

StudentId INT AUTO_INCREMENT,  
FirstName VARCHAR(100) NOT NULL,
LastName VARCHAR(100) NOT NULL,
Class VARCHAR(20) NOT NULL,
City VARCHAR(20) NOT NULL,
State VARCHAR(20) NOT NULL,
PinNo INT  NOT NULL,
PRIMARY KEY(StudentId )

);

```

现在向学生表中插入一些数据:

```sql
INSERT INTO  
Student(FirstName, LastName, Class, City, State, PinNo )
VALUES
('Sayantan', 'Maity', 'X', 'Kolkata', 'WestBengal', 700001 ),
('Nitin', 'Shah', 'XI', 'Jalpaiguri', 'WestBengal', 735102 ),
('Aniket', 'Sharma', 'XI', 'Midnapore', 'WestBengal', 721211 ),
('Abdur', 'Ali', 'X', 'Malda', 'WestBengal', 732101 ),
('Sanjoy', 'Sharama', 'X', 'Kolkata', 'WestBengal', 700004 ) ;

```

学生表是:

```sql
Select * From Student ;

```

| 学生编号 | 西方人名的第一个字 | 姓 | 班级 | 城市 | 状态 | 平诺 |
| --- | --- | --- | --- | --- | --- | --- |
| one | 萨彦坦 | 迈蒂 | X | 加尔各答 | 西孟加拉国 | Seven hundred thousand and one |
| Two | 尼廷 | 沙 | 希腊字母的第 14 个字母 | Jalpaiguri | 西孟加拉国 | Seven hundred and thirty-five thousand one hundred and two |
| three | 阿尼克特 | 夏尔马 | 希腊字母的第 14 个字母 | 米德纳波雷 | 西孟加拉国 | Seven hundred and twenty-one thousand two hundred and eleven |
| four | 阿卜杜尔 | 阿里 | X | 马尔达 | 西孟加拉国 | Seven hundred and thirty-two thousand one hundred and one |
| five | Sanjoy | 沙拉玛 | X | 加尔各答 | 西孟加拉国 | Seven hundred thousand and four |

现在，我们将使用 CONCAT 函数连接名字和姓氏以获得全名和城市、州和 PinNo 以获得地址。

```sql
Select 
    StudentId, FirstName, LastName, 
    CONCAT(FirstName, ' ', LastName) AS FullName,
    CONCAT(City, ' ', State, ' ', PinNO) AS Address

    FROM Student;    

```

**输出:**

| 学生编号 | 西方人名的第一个字 | 姓 | 表 | 地址 |
| --- | --- | --- | --- | --- |
| one | 萨彦坦 | 迈蒂 | 沙坦迈蒂 | 加尔各答西孟加拉邦 7000001 |
| Two | 尼廷 | 沙 | 尼廷沙阿 | 贾派古里西孟加拉 735102 |
| three | 阿尼克特 | 夏尔马 | 阿尼克·夏尔马 | midnapore westbengal 721211 |
| four | 阿卜杜尔 | 阿里 | 阿卜杜尔阿里 | 马尔达西孟加拉 732101 |
| five | Sanjoy | 沙拉玛 | 桑乔伊·沙拉玛 | 加尔各答西孟加拉邦 7000004 |