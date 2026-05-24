# MySQL 中的 RAND()函数

> 原文:[https://www.geeksforgeeks.org/rand-function-in-mysql/](https://www.geeksforgeeks.org/rand-function-in-mysql/)

MySQL 中的 **RAND** ()函数用于返回范围 **0 < = V < 1.0** 内的随机浮点值 **V** 。如果我们想获得一个在 **i < = R < j** 范围内的随机整数 R，我们必须使用表达式:
**FLOOR(I+RAND()*(j-I))**。

**语法:**

```sql
RAND(N)
```

**参数:**此方法只接受一个参数。
**N :** 如果指定了 N，它将返回一个可重复的随机数序列。如果没有指定 N，它将返回一个完全随机的数字。它是可选的，可以作为种子值。
**返回:**返回 0 到 1 之间的随机浮点数。

**示例-1 :**
使用 RAND 函数获取 0 到 1 之间的随机值。

```sql
SELECT RAND() AS Random_Number;
```

**输出:**

| 随机数 |
| --- |
| 0.6332025068189973 |

**示例-2 :**
使用带有种子值的 RAND 函数获取 0 到 1 之间的随机值。

```sql
SELECT RAND(), RAND(5), RAND(5);
```

**输出:**

| 兰德(美国) | 兰德(5) | 兰德(5) |
| --- | --- | --- |
| 0.9580191140603452 | 0.40613597483014313 | 0.40613597483014313 |

因此，在这里我们可以看到，如果我们使用相同的种子值来生成随机数，我们将得到相同的随机数作为结果。

**示例-3 :**
使用兰德函数获取**【5，10】**范围内的随机值。这里，我们将使用表达式:**FLOOR(I+RAND()*(j-I))**来生成随机数。在这里，我 5 岁，j 10 岁。

```sql
SELECT FLOOR(5 + RAND()*(10-5)) AS Random_Number;
```

**输出:**

| 随机数 |
| --- |
| six |

**示例-4 :**
使用兰德函数获取**【5，10】**范围内的随机值。这里，我们将使用表达式:**FLOOR(I+RAND()*(j I+1))**来生成随机数。这里 **i** 为 5， **j** 为 10。

```sql
SELECT FLOOR(5 + RAND()*(10 - 5 + 1)) AS Random_Number;
```

**输出:**

| 随机数 |
| --- |
| Ten |

**示例-5 :**
使用 RAND 函数按随机顺序从类别表中返回行。为了演示，创建一个名为**学生**的表格。

```sql
CREATE TABLE Student(
          Student_id INT AUTO_INCREMENT,  
          Student_name VARCHAR(100) NOT NULL,
          Student_Class VARCHAR(20) NOT NULL,
          TotalExamGiven INT   NOT NULL,
          PRIMARY KEY(Student_id )
);
```

现在向学生表中插入一些数据–

```sql
INSERT INTO  
          Student(Student_name, Student_Class, TotalExamGiven)
VALUES
          ('Sayan', 'IX', 8),
          ('Nitin', 'X', 5),
          ('Aniket', 'XI', 6),
          ('Abdur', 'X', 7),
          ('Riya', 'IX', 4),
          ('Jony', 'X', 10),
          ('Deepak', 'X', 7),
          ('Ankana', 'XII', 5),
          ('Shreya', 'X', 8);
```

要获得学生表的所有详细信息，我们将使用–

```sql
SELECT * 
FROM Student;
```

**输出:**

| 学生 id | 学生名称 | 学生 _ 班级 | totalexamplegiven |
| --- | --- | --- | --- |
| one | Sayan | 离子交换 | eight |
| Two | 尼廷 | X | five |
| three | 阿尼克特 | 希腊字母的第 14 个字母 | six |
| four | 阿卜杜尔 | X | seven |
| five | 里亚 | 离子交换 | four |
| six | 琼尼 | X | Ten |
| seven | 迪帕克（男子名） | X | seven |
| eight | 安卡拉 | 罗马数字 12 | five |
| nine | 施莱 | X | eight |

因此，我们可以看到表中的所有行都是以正确的顺序给出的。要按随机顺序从学生表中返回行，我们将使用–

```sql
SELECT * 
FROM Student 
ORDER BY RAND();
```

**输出:**

| 学生 id | 学生名称 | 学生 _ 班级 | totalexamplegiven |
| --- | --- | --- | --- |
| six | 琼尼 | X | Ten |
| one | Sayan | 离子交换 | eight |
| five | 里亚 | 离子交换 | four |
| Two | 尼廷 | X | five |
| three | 阿尼克特 | 希腊字母的第 14 个字母 | six |
| eight | 安卡拉 | 罗马数字 12 | five |
| nine | 施莱 | X | eight |
| four | 阿卜杜尔 | X | seven |
| seven | 迪帕克（男子名） | X | seven |