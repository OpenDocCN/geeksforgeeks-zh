# MySQL 中的 MID()函数

> 原文:[https://www.geeksforgeeks.org/mid-function-in-mysql/](https://www.geeksforgeeks.org/mid-function-in-mysql/)

**MID() :**

MySQL 中的函数用于从给定的输入字符串中提取一个子串。如果起始位置是正数，那么给定长度的子串将从起始索引中提取。如果为负，那么给定长度的子字符串将从结束索引中提取。

**语法:**

```sql
MID(str,pos,len)
```

**参数:**

该函数接受 3 个参数。

*   **str–**
    我们想要从中提取子串的字符串。
*   **pos–**
    表示输入字符串中开始提取的位置。
*   **len–**
    表示我们要提取的字符串的长度。

**返回:**
从给定的输入字符串中提取一个子串。

**示例-1 :**

从位置 1 开始，借助 MID 函数，从字符串“geeksforgeeks”中提取长度为 5 的字符串。

```sql
SELECT MID('geeksforgeeks', 1, 5) As SUBSTRING;
```

**输出:**

<figure class="table">

| 子链 |
| --- |
| geek |

</figure>

**示例-2 :**

在从位置 3 开始的 MID 函数的帮助下，从字符串“学习 MySQL 很有趣”中提取长度为 3 的字符串。

```sql
SELECT MID('Learning MySQL is fun', -3, 3) As SUBSTRING;
```

**输出:**

<figure class="table">

| 子链 |
| --- |
| 乐趣 |

</figure>

**示例-3 :**

中间函数也可以用于列数据。

**创建学生表–**

```sql
CREATE TABLE StudentDetails
(
Student_id INT AUTO_INCREMENT,  
Student_name VARCHAR(100) NOT NULL,
Roll INT NOT NULL,
Department VARCHAR(10) NOT NULL,
PRIMARY KEY(Student_id )
);
```

**将值插入表格–**

```sql
INSERT INTO StudentDetails
(Student_name ,Roll, Department )
VALUES
('Anik Biswas ',10100,'CSE'),
('Bina Mallick', 11000,'ECE' ),
('Niket Sharma', 12000,'IT' ),
('Sayan Samanta',13000, 'ME'  ),
('Riya Shah ', 14000,'EE' ),  
('Bipin Kohli', 15000,'CE' );
```

表格将如下所示。

```sql
SELECT  * from StudentDetails;
```

<figure class="table">

| 学生标识 | 学生姓名 | 卷 | 部门 |
| --- | --- | --- | --- |
| one | 阿尼克·比斯瓦斯 | Ten thousand one hundred | 中学生毕业考试 |
| Two | 构建马利克 | Eleven thousand | 欧洲经济委员会 |
| three | 夏尔马悲伤 | Twelve thousand | 信息技术 |
| four | 萨扬·萨曼塔 | Thirteen thousand | 我 |
| five | 理雅沙 | Fourteen thousand | 电子工程师 |
| six | 比平·科里 | Fifteen thousand | 这一个 |

</figure>

现在，我们将使用学生名列上的 MID 函数来查找每个学生的名字。

```sql
SELECT Student_id , MID(Student_name,1,5 ) AS First_Name,
Student_name ,Roll,Department FROM StudentDetails;
```

**输出:**

<figure class="table">roll

|  | [Student id] | 【名字】 | [Student name] | four | 【说一个】 | 【说一个萨曼塔】 | 【13000】 | 【我】 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 5【t】 |
| --- |

</figure>