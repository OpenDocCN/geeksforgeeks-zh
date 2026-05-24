# MySQL 中的 CONCAT() 函数

> 原文: [https://www.geeksforgeeks.org/concat-function-in-mysql/](https://www.geeksforgeeks.org/concat-function-in-mysql/)

`CONCAT()` 函数用于连接给定的参数。它可能有一个或多个参数。如果所有参数都是非二进制字符串，则结果是非二进制字符串。如果参数包含任何二进制字符串，则结果为二进制字符串。如果给定了一个数字参数，那么它将被转换为等效的非二进制字符串形式。

## 语法

```sql
CONCAT(str1, str2, ...)
```

## 参数

该方法接受 N 个参数。

*   `str1, str2, str3…`: 我们想要连接的输入字符串。

## 返回

串联所有输入字符串后返回一个新字符串。如果任何输入字符串为空，则返回空值。

## 示例-1

使用 `CONCAT` 函数连接 3 个字符串。

```sql
SELECT CONCAT('geeks', 'for', 'geeks') AS ConcatenatedString ;
```

**输出:**

| ConcatenatedString |
| --- |
| geeksforgeeks |

## 示例-2

使用 `CONCAT` 函数连接数字字符串。

```sql
SELECT CONCAT(19, 10, 5.60) AS ConcatenatedNumber ;
```

**输出:**

| ConcatenatedNumber |
| --- |
| 19105.60 |

## 示例-3

使用 `CONCAT` 函数连接包含空字符串的字符串。

```sql
SELECT CONCAT('geeks', 'for', 'geeks', NULL) AS ConcatenatedString ;
```

**输出:**

| ConcatenatedString |
| --- |
| NULL |

## 示例-4

在本例中，我们将在表的列之间连接字符串。为了演示，创建一个名为 `Student` 的表。

```sql
CREATE TABLE Student(
    StudentId INT AUTO_INCREMENT,
    FirstName VARCHAR(100) NOT NULL,
    LastName VARCHAR(100) NOT NULL,
    Class VARCHAR(20) NOT NULL,
    City VARCHAR(20) NOT NULL,
    State VARCHAR(20) NOT NULL,
    PinNo INT NOT NULL,
    PRIMARY KEY(StudentId)
);
```

现在向学生表中插入一些数据:

```sql
INSERT INTO Student(FirstName, LastName, Class, City, State, PinNo)
VALUES
    ('Sayantan', 'Maity', 'X', 'Kolkata', 'WestBengal', 700001),
    ('Nitin', 'Shah', 'XI', 'Jalpaiguri', 'WestBengal', 735102),
    ('Aniket', 'Sharma', 'XI', 'Midnapore', 'WestBengal', 721211),
    ('Abdur', 'Ali', 'X', 'Malda', 'WestBengal', 732101),
    ('Sanjoy', 'Sharama', 'X', 'Kolkata', 'WestBengal', 700004);
```

学生表是:

```sql
Select * From Student;
```

| StudentId | FirstName | LastName | Class | City | State | PinNo |
| --- | --- | --- | --- | --- | --- | --- |
| 1 | Sayantan | Maity | X | Kolkata | WestBengal | 700001 |
| 2 | Nitin | Shah | XI | Jalpaiguri | WestBengal | 735102 |
| 3 | Aniket | Sharma | XI | Midnapore | WestBengal | 721211 |
| 4 | Abdur | Ali | X | Malda | WestBengal | 732101 |
| 5 | Sanjoy | Sharama | X | Kolkata | WestBengal | 700004 |

现在，我们将使用 `CONCAT` 函数连接名字和姓氏以获得全名，以及城市、州和 `PinNo` 以获得地址。

```sql
Select
    StudentId, FirstName, LastName,
    CONCAT(FirstName, ' ', LastName) AS FullName,
    CONCAT(City, ' ', State, ' ', PinNo) AS Address
FROM Student;
```

**输出:**

| StudentId | FirstName | LastName | FullName | Address |
| --- | --- | --- | --- | --- |
| 1 | Sayantan | Maity | Sayantan Maity | Kolkata WestBengal 700001 |
| 2 | Nitin | Shah | Nitin Shah | Jalpaiguri WestBengal 735102 |
| 3 | Aniket | Sharma | Aniket Sharma | Midnapore WestBengal 721211 |
| 4 | Abdur | Ali | Abdur Ali | Malda WestBengal 732101 |
| 5 | Sanjoy | Sharama | Sanjoy Sharama | Kolkata WestBengal 700004 |