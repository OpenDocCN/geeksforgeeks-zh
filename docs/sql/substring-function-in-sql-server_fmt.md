# SQL Server 中的 SUBSTRING() 函数

> 原文: `https://www.geeksforgeeks.org/substring-function-in-sql-server/`

`SUBSTRING()`函数从输入字符串中给定长度的位置开始提取子字符串。在子字符串的情况下，您需要一个输入字符串，并且需要提到字符串的起点和总长度。

```sql
Input  : String, start, length
output : substring.
```

## 语法

```sql
SUBSTRING(input_string, start, length);
```

## 参数

`SUBSTRING` 函数接受 `STRING`、`start`、`length` 三个参数。让我们看看。

*   `input_string` – 可以是字符、二进制、文本、ntext 或图像表达式。
*   `start` – 它是一个整数，定义返回的子字符串开始的位置。字符串中的第一个位置是 1。
*   `length` – 它是一个正整数，指定要从子字符串返回的字符数。

## 返回

从输入字符串的某个位置开始，返回指定长度的子字符串。

## 示例-1

使用带有文字字符串的 `SUBSTRING()` 函数。

```sql
SELECT SUBSTRING('SQL In Geeksforgeeks', 7, 18 ) 
AS ExtractString;
```

**输出:**

| ExtractString |
| :--- |
| Geeksforgeeks |

## 示例-2

使用 `SUBSTRING()` 函数处理表列。

**表名 - `Player_Details`**

| **PlayerId** | **PlayerName** | **City** |
| :--- | :--- | :--- |
| 45 | Rohit Sharma | Mumbai |
| 18 | Virat Kohli | Bangalore |
| 7 | MS Dhoni | Chennai |
| 33 | Hardik Pandya | Mumbai |
| 42 | Shikhar Dhawan | Delhi |

```sql
SELECT SUBSTRING(PlayerName, 1, 5) AS ExtractString
FROM Player_Details;
```

**输出:**

| ExtractString |
| :--- |
| Rohit |
| Virat |
| MS Dh |
| Hardi |
| Shikh |