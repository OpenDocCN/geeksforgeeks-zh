# MySQL 中的 LEAST() 函数

> 原文: [https://www.geeksforgeeks.org/least-function-in-mysql/](https://www.geeksforgeeks.org/least-function-in-mysql/)

`LEAST()` 函数在 MySQL 中用于从给定的参数中寻找最小值。如果任何给定值为 `NULL`，它将返回 `NULL`。否则返回最小值。

## 语法

```sql
LEAST(X1, X2, X3, ...)
```

## 参数

该方法接受 N 个参数：

*   `X1, X2, X3 ...`: 需要计算最小值的值列表。

## 返回

返回最小值。

## 示例-1

使用 `LEAST()` 函数查找给定数字之间的最小数字。

```sql
SELECT LEAST(10, 20, 30, 40) AS Least_Value;
```

**输出:**

```sql
+-------------+
| Least_Value |
+-------------+
|          10 |
+-------------+
```

## 示例-2

使用 `LEAST()` 函数查找给定字符串之间的最小值。

```sql
SELECT LEAST( 'MySQL', 'MS ACCESS', 'SQL') AS LeastValue_String;
```

**输出:**

```sql
+-------------------+
| LeastValue_String |
+-------------------+
| MS ACCESS         |
+-------------------+
```

## 示例-3

`LEAST()` 函数也可以用来求列数据的最小值。演示创建一个名为 `Student` 的表。

现在在 `Student` 表中插入一些数据：

```sql
INSERT INTO  
    Student(Student_name, Student_Class, Subject1, Subject2, Subject3, Subject4)
VALUES
    ('Sayan', 'X', 81, 90, 86, 98 ),
    ('Nitin', 'X', 90, 84, 88, 90 ),
    ('Aniket', 'X', 81, 80, 87, 90 ),
    ('Abdur', 'X', 85, 90, 80, 90  ),
    ('Sanjoy', 'X', 88, 82, 84, 90 ) ;
```

所以，我们的表看起来像：

```sql
+------------+--------------+---------------+----------+----------+----------+----------+
| Student_id | Student_name | Student_Class | Subject1 | Subject2 | Subject3 | Subject4 |
+------------+--------------+---------------+----------+----------+----------+----------+
|          1 | Sayan        | X             |       81 |       90 |       86 |       98 |
|          2 | Nitin        | X             |       90 |       84 |       88 |       90 |
|          3 | Aniket       | X             |       81 |       80 |       87 |       90 |
|          4 | Abdur        | X             |       85 |       90 |       80 |       90 |
|          5 | Sanjoy       | X             |       88 |       82 |       84 |       90 |
+------------+--------------+---------------+----------+----------+----------+----------+
```

现在，我们将在所有科目中为每个学生找到最低分。

```sql
SELECT 
    Student_id, Student_name, LEAST(Subject1, Subject2, Subject3, Subject4) as Least_Mark 
FROM Student;
```

**输出:**

```sql
+------------+--------------+------------+
| Student_id | Student_name | Least_Mark |
+------------+--------------+------------+
|          1 | Sayan        |         81 |
|          2 | Nitin        |         84 |
|          3 | Aniket       |         80 |
|          4 | Abdur        |         80 |
|          5 | Sanjoy       |         82 |
+------------+--------------+------------+
```