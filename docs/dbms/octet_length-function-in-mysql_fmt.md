# MySQL 中的 `OCTET_LENGTH()` 函数

> 原文: [https://www.geeksforgeeks.org/octet_length-function-in-mysql/](https://www.geeksforgeeks.org/octet_length-function-in-mysql/)

在本文中，我们将介绍 `OCTET_LENGTH` 函数。并将看到 `OCTET_LENGTH` 函数的语法和示例。我们一个一个来讨论。

## 介绍

`OCTET_LENGTH` 函数在 MySQL 中用来返回给定字符串中的字符数。

## 语法

```
OCTET_LENGTH( str )
```

## 参数

这个函数接受一个参数，如上面语法中提到的和下面例子中描述的。

*   `str`: 要查找其字符数的给定字符串。

## 返回值

返回给定字符串的长度。

## 示例-1

对字符串应用 `OCTET_LENGTH()` 函数。

```
SELECT OCTET_LENGTH('geeksforgeeks') 
as String_Length;
```

**输出:**

| String_Length |
| --- |
| 13 |

## 示例-2

将 `OCTET_LENGTH()` 函数应用于数字字符串。

```
SELECT OCTET_LENGTH(56432) 
as Length;
```

**输出:**

| Length |
| --- |
| 5 |

## 示例-3

将 `OCTET_LENGTH()` 函数应用于表中的列。

**表格: Student_Details**

| Student_ID | Student_Name |
| --- | --- |
| 134500 | Ramesh Singh |
| 134501 | Arunima Rao |
| 134502 | Shreya Sharma |
| 134503 | Leena Tellur |

找出每个学生姓名的总长度(包括一个空格)。

```
SELECT OCTET_LENGTH(Student_Name) as Name_Length 
FROM Student_Details ;
```

**输出:**

| Name_Length |
| --- |
| 10 |
| 11 |
| 13 |
| 12 |