# MySQL 中的 LPAD()函数

> 原文:[https://www.geeksforgeeks.org/lpad-function-in-mysql/](https://www.geeksforgeeks.org/lpad-function-in-mysql/)

**LPAD**()MySQL 中的函数用于在原字符串的左侧填充或添加一个字符串。

**语法:**

```sql
LPAD(str, len, padstr)
```

**参数:**该功能接受三个参数，如上所述，描述如下–

*   **str** – 
    The actual string which is to be padded. If the length of the original string is larger than the len parameter, this function removes the overfloating characters from string. 
*   **len** – 
    This is the length of a final string after the left padding. 
*   **padstr** – 
    String that to be added to the left side of the Original Str. 

**返回**:填充后返回一个新的 len 长度字符串。

**示例-1 :** 将 LPAD()函数应用于字符串以获得新的填充字符串。

```sql
SELECT LPAD("geeksforgeeks", 20, "*") AS LeftPaddedString;
```

**输出:**

<figure class="table">

| 左 paddedstring |
| --- |
| * * * * * * * *极客伪造 |

</figure>

**示例-2 :** 当原始字符串大于 len 参数时，对字符串应用 LPAD()函数。

```sql
SELECT LPAD("geeksforgeeks", 10, "*") AS LeftPaddedString;
```

**输出:**

<figure class="table">

| 左 paddedstring |
| --- |
| 极客锻造 |

</figure>

**示例-3 :** LPAD 函数也可以用来为列数据添加字符串。为了演示，创建一个名为 Student 的表。

```sql
CREATE TABLE Student
(
Student_id INT AUTO_INCREMENT,  
Student_name VARCHAR(100) NOT NULL,
Student_Class VARCHAR(20) NOT NULL,
PRIMARY KEY(Student_id )
);
```

**现在向学生表中插入一些数据:**

```sql
INSERT INTO Student
(Student_name, Student_Class)
VALUES
('Ananya Majumdar', 'IX'),
('Anushka Samanta', 'X'),
('Aniket Sharma', 'XI'),
('Anik Das', 'X'),
('Riya Jain', 'IX'),
('Tapan Samanta', 'X');
```

学生表如下。

| Student id | Student name |  |
| --- | --- | --- |

现在，我们将向 Student_Class 列中显示的每个字符串添加一些字符串。

```sql
SELECT Student_id, Student_name,
LPAD(Student_Class, 10, ' _') AS LeftPaddedString
FROM Student;
```

**输出:**

| [Student id] | [Student name] | 【左舵驾驶】 |
| --- | --- | --- |
| Yazhai |  |
|  | 【tapan samanta】 |  |