# MySQL 中的 CHAR_LENGTH() 函数

> 原文: [https://www.geeksforgeeks.org/char_length-function-in-mysql/](https://www.geeksforgeeks.org/char_length-function-in-mysql/)

`CHAR_LENGTH()` 函数用于查找给定字符串的长度（以字符为单位）。它计算字符数，忽略字符是单字节还是多字节。

## 语法

```sql
CHAR_LENGTH(str)
```

## 参数

该方法接受一个参数：

*   `str`: 需要计算长度的字符串。

## 返回值

返回给定字符串的长度。

## 示例

### 示例-1：查找字符串的长度

```sql
SELECT CHAR_LENGTH("geeksforgeeks") AS LengthOfString
```

**输出：**

| LengthOfString |
| :------------ |
| 13            |

### 示例-2：查找包含空格的字符串长度

```sql
SELECT CHAR_LENGTH("SQL Tutorial in geeksforgeeks") AS LengthOfString
```

**输出：**

| LengthOfString |
| :------------ |
| 29            |

### 示例-3：查找表中一列每个字符串的长度

**表：Student_details**

| Student_id | Student_name | Total_marks |
| :--------- | :----------- | :---------- |
| 1          | Amit         | 450         |
| 2          | Aniket       | 470         |
| 3          | Aishwarya    | 490         |

```sql
SELECT Student_name, CHAR_LENGTH(Student_name) AS Length_name FROM Student_details;
```

**输出：**

| Student_name | Length_name |
| :----------- | :---------- |
| Amit         | 4           |
| Aniket       | 6           |
| Aishwarya    | 9           |