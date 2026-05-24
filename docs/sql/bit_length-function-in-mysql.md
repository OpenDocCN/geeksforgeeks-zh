# MySQL 中的 BIT_LENGTH()函数

> 原文:[https://www.geeksforgeeks.org/bit_length-function-in-mysql/](https://www.geeksforgeeks.org/bit_length-function-in-mysql/)

**BIT_LENGTH** ()函数在 MySQL 中用于查找给定字符串的长度，单位为比特。输入字符串可以是字符串或数字字符串。

**语法:**

```sql
BIT_LENGTH(str)
```

**参数:**必选。
**字符串:**需要计算位长的字符串。
**返回:**以位为单位返回给定字符串的长度。

**示例-1 :**
BIT_LENGTH()函数查找字符串的位长。

```sql
SELECT BIT_LENGTH("geeksforgeeks") AS BitLengthOfString;
```

**输出:**

| 位长度字符串 |
| --- |
| One hundred and four |

**示例-2 :**
BIT_LENGTH()函数查找数字字符串的位长。

```sql
SELECT BIT_LENGTH(2020) AS BitLengthOfString;
```

**输出:**

| 位长度字符串 |
| --- |
| Thirty-two |

**示例-3 :**
BIT_LENGTH()函数，用于查找表的一列中每个字符串的位长。

**表–**学生 _ 详细信息

| 学生标识 | 学生名 |
| --- | --- |
| one | Amit |
| Two | 传承 |
| three | 维拉特 |
| four | rohit！rohit |
| five | 艾什瓦里亚 |

```sql
SELECT BIT_LENGTH(Student_Name) AS BitLengthOfName 
FROM Student_Details;
```

**输出:**

| BitLengthOfName |
| --- |
| Thirty-two |
| Forty-eight |
| Forty |
| Forty |
| seventy-two |