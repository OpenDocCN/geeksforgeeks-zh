# MySQL 中的 `LPAD()` 函数

> 原文: [https://www.geeksforgeeks.org/lpad-function-in-mysql/](https://www.geeksforgeeks.org/lpad-function-in-mysql/)

`LPAD()` 函数用于在原字符串的左侧填充或添加一个字符串。

## 语法

```sql
LPAD(str, len, padstr)
```

## 参数

该功能接受三个参数，描述如下：

*   `str` – 要填充的实际字符串。如果原始字符串的长度大于 `len` 参数，此函数会从字符串中移除溢出的字符。
*   `len` – 左填充后最终字符串的长度。
*   `padstr` – 要添加到原始字符串左侧的字符串。

## 返回值

填充后返回一个新的 `len` 长度字符串。

## 示例

### 示例-1：将 `LPAD()` 函数应用于字符串以获得新的填充字符串

```sql
SELECT LPAD("geeksforgeeks", 20, "*") AS LeftPaddedString;
```

**输出:**

| LeftPaddedString |
| --- |
| *********geeksforgeeks |

### 示例-2：当原始字符串大于 `len` 参数时，对字符串应用 `LPAD()` 函数

```sql
SELECT LPAD("geeksforgeeks", 10, "*") AS LeftPaddedString;
```

**输出:**

| LeftPaddedString |
| --- |
| geeksforge |

### 示例-3：为列数据添加字符串

`LPAD` 函数也可以用来为列数据添加字符串。为了演示，创建一个名为 `Student` 的表。

```sql
CREATE TABLE Student
(
Student_id INT AUTO_INCREMENT,  
Student_name VARCHAR(100) NOT NULL,
Student_Class VARCHAR(20) NOT NULL,
PRIMARY KEY(Student_id)
);
```

现在向 `Student` 表中插入一些数据：

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

`Student` 表如下。

| Student_id | Student_name | Student_Class |
| --- | --- | --- |
| 1 | Ananya Majumdar | IX |
| 2 | Anushka Samanta | X |
| 3 | Aniket Sharma | XI |
| 4 | Anik Das | X |
| 5 | Riya Jain | IX |
| 6 | Tapan Samanta | X |

现在，我们将向 `Student_Class` 列中显示的每个字符串添加一些字符串。

```sql
SELECT Student_id, Student_name,
LPAD(Student_Class, 10, ' _') AS LeftPaddedString
FROM Student;
```

**输出:**

| Student_id | Student_name | LeftPaddedString |
| --- | --- | --- |
| 1 | Ananya Majumdar | ________IX |
| 2 | Anushka Samanta | ________X |
| 3 | Aniket Sharma | _______XI |
| 4 | Anik Das | ________X |
| 5 | Riya Jain | ________IX |
| 6 | Tapan Samanta | _______X |