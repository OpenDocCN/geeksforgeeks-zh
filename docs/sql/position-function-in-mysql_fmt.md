# MySQL 中的 POSITION() 函数

> 原文: [https://www.geeksforgeeks.org/position-function-in-mysql/](https://www.geeksforgeeks.org/position-function-in-mysql/)

## `POSITION()`

[MySQL](https://www.geeksforgeeks.org/sql-tutorial/) 中的这个函数用于查找字符串中某个子串的位置。它将返回字符串中第一个出现的子字符串的位置。如果字符串中不存在子字符串，则它将返回 0。当在字符串中搜索子字符串的位置时，该函数不执行区分大小写的搜索。

## 语法

```sql
POSITION(substring IN string)
```

## 参数

该方法接受两个参数

*   `substring` - 要检索其位置的字符串。
*   `string` - 要在其中检索子字符串位置的字符串。

## 返回

字符串中子字符串第一次出现的位置。

## 示例-1

在字符串“geeksforgeeks”中搜索字符串“g”，如下所示。

```sql
SELECT POSITION('g' IN 'geeksforgeeks') AS location;
```

**输出:**

| 位置 |
| --- |
| 1 |

## 示例-2

在字符串“这是一棵树”中搜索字符串“这”，使用如下位置函数。

```sql
SELECT POSITION('this' IN 'That is a tree') AS location;
```

**输出:**

| 位置 |
| --- |
| 0 |

## 示例-3

位置函数也可以用于列数据，如下所示。

### 创建学生表

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

### 将数据插入表格

```sql
INSERT INTO Student
(Student_name ,Roll, Department )
VALUES
('Anik Biswas ',10100,'CSE'),
('Bina Mallick', 11000,'ECE' ),
('Niket Sharma', 12000,'IT' ),
('Sayani Samanta',13000, 'ME'  ),
('Riyanka Shah ', 14000,'EE' ), 
('Bipin Kohli', 15000,'CE' );
```

验证使用如下命令。

```sql
SELECT  * from Student ;
```

**输出:**

| Student_id | Student_name | Roll | Department |
| --- | --- | --- | --- |
| 1 | Anik Biswas | 10100 | CSE |
| 2 | Bina Mallick | 11000 | ECE |
| 3 | Niket Sharma | 12000 | IT |
| 4 | Sayani Samanta | 13000 | ME |
| 5 | Riyanka Shah | 14000 | EE |
| 6 | Bipin Kohli | 15000 | CE |

现在，我们将为每个学生的名字找到字符串“a”的第一次出现。

```sql
SELECT *,POSITION('a' IN Student_name ) AS First_Occ_A  
FROM STUDENT;
```

**输出:**

| Student_id | Student_name | Roll | Department | First_Occ_A |
| --- | --- | --- | --- | --- |
| 1 | Anik Biswas | 10100 | CSE | 1 |
| 2 | Bina Mallick | 11000 | ECE | 2 |
| 3 | Niket Sharma | 12000 | IT | 0 |
| 4 | Sayani Samanta | 13000 | ME | 1 |
| 5 | Riyanka Shah | 14000 | EE | 0 |
| 6 | Bipin Kohli | 15000 | CE | 2 |