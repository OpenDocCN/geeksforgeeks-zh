# MySQL 中的 RTRIM()函数

> 原文:[https://www.geeksforgeeks.org/rtrim-function-in-mysql/](https://www.geeksforgeeks.org/rtrim-function-in-mysql/)

**RTRIM() :**
这是 MySQL 中用来删除字符串尾部空格的函数。

**语法:**

```sql
RTRIM(str)
```

**参数:**
RTRIM()函数接受一个参数，如上所述，如下所述。

*   **字符串–**我们要从中删除尾随空格的字符串。

**返回:**
截断所有尾随空格后返回字符串。

**示例-1 :**
使用 RTRIM 函数移除给定字符串的所有尾随空格。

```sql
SELECT RTRIM ('geeksforgeeks') 
AS RightTrimmedString;  

```

**输出:**

```sql
+----------------------+--------------------+
| geeksforgeeks        | RightTrimmedString |
+----------------------+--------------------+
| geeksforgeeks        | geeksforgeeks      |
+----------------------+--------------------+

```

**示例-2 :**
使用 RTRIM 函数移除给定字符串的所有尾随空格。

```sql
SELECT 'MySQL' AS String, RTRIM ('MySQL') 
AS Tstring;

```

**输出:**

```sql
+----------------------+---------+
| String               | Tstring |
+----------------------+---------+
| MySQL                | MySQL   |
+----------------------+---------+

```

**示例-3 :**
RTRIM 函数也可以用来移除列数据的所有尾随空格。为了演示，创建一个名为 Student 的表。

```sql
CREATE TABLE Student
(
  Student_id INT AUTO_INCREMENT,  
  Student_name VARCHAR(100) NOT NULL,
  Student_Class VARCHAR(20) NOT NULL,
  PRIMARY KEY(Student_id )

);

```

**在学生表中插入一些数据:**

```sql
INSERT INTO Student
(Student_name, Student_Class )
VALUES
  ('Ananya Majumdar     ', 'IX'),
  ('Anushka Samanta    ', 'X' ),
  ('Aniket Sharma   ', 'XI' ),
  ('Anik Das      ', 'X'  ),
  ('Riya Jain   ', 'IX' ),
  ('Tapan Samanta    ', 'X' ),
  ('Deepak Sharma    ', 'X'  ),
  ('Ankana Jana    ', 'XII'),
  ('Shreya Ghosh    ', 'X') ;

```

学生表如下。

```sql
mysql> select * from Student;

```

**输出:**

```sql
+------------+----------------------+---------------+
| Student_id | Student_name         | Student_Class |
+------------+----------------------+---------------+
|          1 | Ananya Majumdar      | IX            |
|          2 | Anushka Samanta      | X             |
|          3 | Aniket Sharma        | XI            |
|          4 | Anik Das             | X             |
|          5 | Riya Jain            | IX            |
|          6 | Tapan Samanta        | X             |
|          7 | Deepak Sharma        | X             |
|          8 | Ankana Jana          | XII           |
|          9 | Shreya Ghosh         | X             |
+------------+----------------------+---------------+

```

现在，我们将从学生名列中删除所有尾随空格。

```sql
  SELECT  
  Student_id,  Student_name,
  RTRIM( Student_name) AS  TrimmedSname 
  FROM Student ;   

```

**输出:**

```sql
+------------+----------------------+-----------------+
| Student_id | Student_name         | TrimmedSname    |
+------------+----------------------+-----------------+
|          1 | Ananya Majumdar      | Ananya Majumdar |
|          2 | Anushka Samanta      | Anushka Samanta |
|          3 | Aniket Sharma        | Aniket Sharma   |
|          4 | Anik Das             | Anik Das        |
|          5 | Riya Jain            | Riya Jain       |
|          6 | Tapan Samanta        | Tapan Samanta   |
|          7 | Deepak Sharma        | Deepak Sharma   |
|          8 | Ankana Jana          | Ankana Jana     |
|          9 | Shreya Ghosh         | Shreya Ghosh    |
+------------+----------------------+-----------------+

```