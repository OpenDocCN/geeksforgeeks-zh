# MySQL 中的 SOUNDEX()函数

> 原文:[https://www.geeksforgeeks.org/soundex-function-in-mysql/](https://www.geeksforgeeks.org/soundex-function-in-mysql/)

**MySQL 中的 SOUNDEX** ()函数用于返回字符串的语音表示。音标代表字符串的发音方式。SOUNDEX 函数有助于比较拼写不同但在英语中听起来相似的单词。

**语法:**

```sql
SOUNDEX(str)

```

**参数:**
SOUNDEX()函数接受一个参数，如上所述，如下所述。

*   **str :** 我们想知道其语音表示的字符串。

**返回:**
返回给定字符串的语音表示。

**注:**

*   目前实现的这个函数旨在很好地处理仅使用英语的字符串。其他语言的字符串可能不会产生可靠的结果。
*   该函数不能保证为使用多字节字符集(包括 utf-8)的字符串提供一致的结果。

**示例-1 :**
使用 SOUNDEX 函数找到“geeksforgeeks”的 SOUNDEX 字符串。

```sql
SELECT SOUNDEX('geeksforgeeks') AS SoundexString; 

```

**输出:**

| SoundexString |
| --- |
| G162 |

**示例-2 :**
使用 SOUNDEX 函数查找“Hello”的 SOUNDEX 字符串。

```sql
SELECT SOUNDEX('Hello') AS SoundexString; 

```

**输出:**

| SoundexString |
| --- |
| H400 |

**示例-3 :**
SOUNDEX 函数也可以用来查找列数据的 SOUNDEX 字符串。为了演示，创建一个名为 Student 的表。

```sql
CREATE TABLE Student
(
   Student_id INT AUTO_INCREMENT,  
   Student_name VARCHAR(100) NOT NULL,
   Student_Class VARCHAR(20) NOT NULL,
   PRIMARY KEY(Student_id )

);

```

现在向学生表中插入一些数据:

```sql
INSERT INTO Student
(Student_name, Student_Class )
VALUES
   ('Ananya Majumdar', 'IX'),
   ('Anushka Samanta', 'X' ),
   ('Aniket Sharma', 'XI' ),
   ('Anik Das', 'X'  ),
   ('Riya Jain', 'IX' ),
   ('Tapan Samanta', 'X' ),
   ('Deepak Sharma', 'X'  ),
   ('Ankana Jana', 'XII'),
   ('Shreya Ghosh', 'X') ;

```

**那么，学生表如下。**

```sql
mysql> select * from Student;
+------------+-----------------+---------------+
| Student_id | Student_name    | Student_Class |
+------------+-----------------+---------------+
|          1 | Ananya Majumdar | IX            |
|          2 | Anushka Samanta | X             |
|          3 | Aniket Sharma   | XI            |
|          4 | Anik Das        | X             |
|          5 | Riya Jain       | IX            |
|          6 | Tapan Samanta   | X             |
|          7 | Deepak Sharma   | X             |
|          8 | Ankana Jana     | XII           |
|          9 | Shreya Ghosh    | X             |
+------------+-----------------+---------------+
9 rows in set (0.00 sec)

```

现在，我们将为列 Student_name 找到 SOUNDEX 字符串。

```sql
SELECT  
   Student_id,  Student_name,
   SOUNDEX( Student_name) AS  SoundexSname,
   Student_Class FROM Student ;    

```

**输出:**

```sql
+------------+-----------------+--------------+---------------+
| Student_id | Student_name    | SoundexSname | Student_Class |
+------------+-----------------+--------------+---------------+
|          1 | Ananya Majumdar | A52536       | IX            |
|          2 | Anushka Samanta | A5253        | X             |
|          3 | Aniket Sharma   | A523265      | XI            |
|          4 | Anik Das        | A5232        | X             |
|          5 | Riya Jain       | R250         | IX            |
|          6 | Tapan Samanta   | T15253       | X             |
|          7 | Deepak Sharma   | D1265        | X             |
|          8 | Ankana Jana     | A52525       | XII           |
|          9 | Shreya Ghosh    | S620         | X             |
+------------+-----------------+--------------+---------------+

```