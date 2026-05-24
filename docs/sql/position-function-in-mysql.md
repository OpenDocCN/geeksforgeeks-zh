# MySQL 中的 POSITION()函数

> 原文:[https://www.geeksforgeeks.org/position-function-in-mysql/](https://www.geeksforgeeks.org/position-function-in-mysql/)

**位置():**

[MySQL](https://www.geeksforgeeks.org/sql-tutorial/) 中的这个函数用于查找字符串中某个子串的位置。它将返回字符串中第一个出现的子字符串的位置。如果字符串中不存在子字符串，则它将返回 0。当在字符串中搜索子字符串的位置时，该函数不执行区分大小写的搜索。

**语法:**

```sql
POSITION(substring IN string)
```

**参数:**

该方法接受两个参数

*   **substring-** The string whose position you want to retrieve.
*   **String–** The string whose substring position is to be retrieved.

**返回:**

字符串中子字符串第一次出现的位置。

**示例-1 :**

在字符串“geeksforgeeks”中搜索字符串“g”，如下所示。

```sql
SELECT POSITION('g' IN 'geeksforgeeks') AS location;
```

**输出:**

<figure class="table">T5】

| 位置 |
| --- |
| 1 |

</figure>

**示例-2 :**

在字符串“这是一棵树”中搜索字符串“这”，使用如下位置函数。

```sql
SELECT POSITION('this' IN 'That is a tree') AS location;
```

**输出:**

<figure class="table">T5】

| 位置 |
| --- |
| 0 |

</figure>

**示例-3 :**

位置函数也可以用于列数据，如下所示。

**创建学生表:**

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

**将数据插入表格:**

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

<figure class="table">部门

|  | [Student id] | [Student name] | 【滚】 |
| --- | --- | --- | --- |
| five | 【里雅卡沙阿】 | 【14000】 |  |
|  | "叮叮" |

</figure>

现在，我们将为每个学生的名字找到字符串“a”的第一次出现。

```sql
SELECT *,POSITION('a' IN Student_name ) AS First_Occ_A  
FROM STUDENT;
```

**输出:**

<figure class="table">部门

|  | [Student id] | [Student name] | 【滚】 | 萨尼·萨曼塔 | 【13000】 | 【我】 |  |  | 里雅卡沙阿] |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |

</figure>