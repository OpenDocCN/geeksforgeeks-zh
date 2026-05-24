# MySQL 中的 MOD()函数

> 原文:[https://www.geeksforgeeks.org/mod-function-in-mysql/](https://www.geeksforgeeks.org/mod-function-in-mysql/)

MySQL 中的 MOD() [函数用来求一个数除以另一个数的余数。MOD()函数返回被除数除以除数的余数。如果除数为零，则返回 NULL。](https://www.geeksforgeeks.org/sql-functions-aggregate-scalar-functions/)

**语法:**

```sql
MOD(N, M)
or
N % M
or
N MOD M

```

**参数:**
MOD()函数接受两个参数，如上所述，如下所述。

*   **N–**被除数，即一个数或一个将被 m 除的数值表达式
*   **M–**除数，即除以被除数的数字或数值表达式。

**返回:**
返回被除数除以除数的余数。

**例-1 :**
用 MOD 函数求 36 除以 6 的余数。

```sql
SELECT MOD( 36, 6) AS Remainder;

```

**输出:**

| 剩余物 |
| --- |
| Zero |

**示例-2 :**
使用模数运算符(%)求 27 除以 4 后的余数。

```sql
SELECT 27 % 4 AS Remainder;

```

**输出:**

| 剩余物 |
| --- |
| three |

**示例-3 :**
使用 MOD 函数求浮点数的余数。

```sql
SELECT 10.15 MOD 3  AS Remainder;

```

**输出:**

| 剩余物 |
| --- |
| One point one five |

**示例-4 :**
当除数为 0 时，使用 MOD 函数求一个数的余数。

```sql
SELECT MOD( 6, 0) AS Remainder;

```

**输出:**

| 剩余物 |
| --- |
| 空 |

**示例-5 :**
MOD 函数也可用于查找列数据的余数值。在这个例子中，我们将在 MOD 函数的帮助下找到一个学生是否出现了总共奇数次考试或者偶数次考试。为了演示，创建一个名为**学生的表格。**

```sql
CREATE TABLE Student
(
    Student_id INT AUTO_INCREMENT,  
    Student_name VARCHAR(100) NOT NULL,
    Student_Class VARCHAR(20) NOT NULL,
    TotalExamGiven INT   NOT NULL,
    PRIMARY KEY(Student_id )

);

```

**现在向学生表中插入一些数据:**

```sql
INSERT INTO Student
(Student_name, Student_Class, TotalExamGiven )
VALUES
    ('Sayan', 'IX', 8 ),
    ('Nitin', 'X',  5 ),
    ('Aniket', 'XI', 6 ),
    ('Abdur', 'X',  7 ),
    ('Riya', 'IX', 4 ),
    ('Jony', 'X', 10 ),
    ('Deepak', 'X',  7 ),
    ('Ankana', 'XII', 5 ),
    ('Shreya', 'X',  8 ) ;

```

学生表如下。

```sql
mysql> SELECT * FROM Student;
+------------+--------------+---------------+----------------+
| Student_id | Student_name | Student_Class | TotalExamGiven |
+------------+--------------+---------------+----------------+
|          1 | Sayan        | IX            |              8 |
|          2 | Nitin        | X             |              5 |
|          3 | Aniket       | XI            |              6 |
|          4 | Abdur        | X             |              7 |
|          5 | Riya         | IX            |              4 |
|          6 | Jony         | X             |             10 |
|          7 | Deepak       | X             |              7 |
|          8 | Ankana       | XII           |              5 |
|          9 | Shreya       | X             |              8 |
+------------+--------------+---------------+----------------+
9 rows in set (0.00 sec)

```

现在，我们来看看一个学生出现的考试总数是奇数还是偶数。

```sql
SELECT 
    Student_name,
    Student_Class,
    TotalExamGiven,
    IF(MOD(TotalExamGiven, 2),
    'Odd','Even') 
    OddOrEven FROM Student ;    

```

**输出:**

```sql
+--------------+---------------+----------------+-----------+
| Student_name | Student_Class | TotalExamGiven | OddOrEven |
+--------------+---------------+----------------+-----------+
| Sayan        | IX            |              8 | Even      |
| Nitin        | X             |              5 | Odd       |
| Aniket       | XI            |              6 | Even      |
| Abdur        | X             |              7 | Odd       |
| Riya         | IX            |              4 | Even      |
| Jony         | X             |             10 | Even      |
| Deepak       | X             |              7 | Odd       |
| Ankana       | XII           |              5 | Odd       |
| Shreya       | X             |              8 | Even      |
+--------------+---------------+----------------+-----------+

```