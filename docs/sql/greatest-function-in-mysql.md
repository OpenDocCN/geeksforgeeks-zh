# MySQL 中最大()函数

> 原文:[https://www.geeksforgeeks.org/greatest-function-in-mysql/](https://www.geeksforgeeks.org/greatest-function-in-mysql/)

**最大**()函数在 MySQL 中分别用于从给定的参数中寻找最大值。如果任何给定值为空，它将返回空值。否则，它返回最大值。

**语法:**

```sql
GREATEST(X1, X2, X3, ...)
```

**参数:**该方法在语法中接受 N 个参数，如上所述，如下所述:
**X1、X2、X3……:**要计算最大值的值列表。
**返回:**返回最大值。

**示例-1 :**
使用最大()函数寻找给定数字之间的最大值。

```sql
SELECT GREATEST(10, 20, 30, 40, 50) AS Greatest_Value;
```

**输出:**

| 最大值 |
| --- |
| Fifty |

**示例-2 :**
使用最大()函数查找给定字符串之间的最大值。

```sql
SELECT GREATEST('MySQL', 'MS ACCESS', 'SQL') AS  GreatestValue_String;
```

**输出:**

| 最大值 _ 字符串 |
| --- |
| 结构化查询语言 |

**示例-3 :**
当存在空值时，使用最大()函数在给定数字之间寻找最大数字。

```sql
SELECT GREATEST(10, 20, 30, 40, 50, NULL) AS Greatest_Value;
```

**输出:**

| 最大值 |
| --- |
| 空 |

**示例-4 :**
最大值函数也可以用来查找列数据之间的最大值。为了演示，创建一个名为**学生**的表格。

```sql
CREATE TABLE Student(
    Student_id INT AUTO_INCREMENT,  
    Student_name VARCHAR(100) NOT NULL,
    Student_Class VARCHAR(20) NOT NULL,
    Subject1 INT  NOT NULL,
    Subject2 INT  NOT NULL,
    Subject3 INT  NOT NULL,
    Subject4 INT  NOT NULL,
    PRIMARY KEY(Student_id )
);
```

现在向学生表中插入一些数据–

```sql
INSERT INTO  
    Student(Student_name, Student_Class, Subject1, Subject2, Subject3, Subject4)
VALUES
    ('Sayan', 'X', 81, 90, 86, 92 ),
    ('Nitin', 'X', 90, 84, 88, 91 ),
    ('Aniket', 'X', 81, 80, 87, 95 ),
    ('Abdur', 'X', 85, 90, 80, 90  ),
    ('Sanjoy', 'X', 88, 82, 84, 90 );
```

显示学生表中的所有数据–

```sql
Select * 
From Student ;
```

| 学生 id | 学生名称 | 学生 _ 班级 | 主题 1 | 主题 2 | 主题 3 | 主题 4 |
| --- | --- | --- | --- | --- | --- | --- |
| one | Sayan | X | Eighty-one | Ninety | Eighty-six | Ninety-two |
| Two | 尼廷 | X | Ninety | Eighty-four | Eighty-eight | Ninety-one |
| three | 阿尼克特 | X | Eighty-one | Eighty | Eighty-seven | Ninety-five |
| four | 阿卜杜尔 | X | eighty-five | Ninety | Eighty | Ninety |
| five | Sanjoy | X | Eighty-eight | Eighty-two | Eighty-four | Ninety |

现在，我们要为每一个学生找到所有科目的最高分。

```sql
Select Student_id, Student_name, 
GREATEST(Subject1, Subject2, Subject3, Subject4) AS Greatest_Mark
FROM Student;
```

**输出:**

| 学生 id | 学生名称 | 最伟大 _ 马克 |
| --- | --- | --- |
| one | Sayan | Ninety-two |
| Two | 尼廷 | Ninety-one |
| three | 阿尼克特 | Ninety-five |
| four | 阿卜杜尔 | Ninety |
| five | Sanjoy | Ninety |