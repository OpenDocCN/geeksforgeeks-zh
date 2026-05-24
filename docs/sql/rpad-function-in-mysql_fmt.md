# MySQL 中的 `RPAD()` 函数

> 原文: [https://www.geeksforgeeks.org/rpad-function-in-mysql/](https://www.geeksforgeeks.org/rpad-function-in-mysql/)

`RPAD()` 函数用于在原字符串的右侧填充或添加一个字符串。

## 语法

```sql
RPAD(str, len, padstr)
```

## 参数

该功能接受三个参数，描述如下：

*   `str`：需要被填充的实际字符串。如果原字符串的长度大于 `len` 参数，此函数会从字符串右侧截断多余字符。
*   `len`：右填充后最终字符串的长度。
*   `padstr`：要添加到原始字符串右侧的字符串。

## 返回值

填充后返回长度为 `len` 的新字符串。

## 示例

### 示例-1

将 `RPAD()` 函数应用于字符串以获得新的填充字符串。

```sql
SELECT RPAD("geeksforgeeks", 20, "*") AS RightPaddedString;
```

**输出：**

| RightPaddedString |
| :--- |
| geeksforgeeks\*\*\*\*\*\*\* |

### 示例-2

当原始字符串长度大于 `len` 参数时，对字符串应用 `RPAD()` 函数。

```sql
SELECT RPAD("geeksforgeeks", 10, "*") AS RightPaddedString;
```

**输出：**

| RightPaddedString |
| :--- |
| geeksforge |

### 示例-3

将 `RPAD()` 函数应用于表中的字符串列。

**表格 - Student_Details：**

| Student_id | Name | Mark |
| :--- | :--- | :--- |
| 1 | John | 85 |
| 2 | Alice | 92 |

```sql
SELECT RPAD(Name, 15, "#") AS RightPadStudentName
FROM Student_Details;
```

**输出：**

| RightPadStudentName |
| :--- |
| John############ |
| Alice########### |