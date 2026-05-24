# MySQL 中的 RPAD()函数

> 原文:[https://www.geeksforgeeks.org/rpad-function-in-mysql/](https://www.geeksforgeeks.org/rpad-function-in-mysql/)

**RPAD**()MySQL 中的函数用于在原字符串的右侧填充或添加一个字符串。

**语法:**

```sql
RPAD(str, len, padstr)
```

**参数:**该功能接受三个参数，如上所述，描述如下:

*   **str :** The actual string which is to be padded. If the length of the original string is larger than the len parameter, this function removes the overfloating characters from string. 
*   **len :** This is the length of a final string after the right padding. 
*   **padstr :** 要添加到原始字符串右侧的字符串。

**返回:**填充后返回长度 len 的新字符串。

**示例-1 :** 将 RPAD()函数应用于字符串以获得新的填充字符串。

```sql
SELECT RPAD("geeksforgeeks", 20, "*") AS RightPaddedString;
```

**输出:**

<figure class="table">

| 右衬垫字符串 |
| --- |
| 极客伪造* * * * * * |

</figure>

**示例-2 :** 当原始字符串大于 len 参数时，对字符串应用 RPAD()函数。

```sql
SELECT RPAD("geeksforgeeks", 10, "*") AS RightPaddedString;
```

**输出:**

<figure class="table">

| 右衬垫字符串 |
| --- |
| 极客锻造 |

</figure>

**示例-3 :** 将 RPAD()函数应用于表中的字符串列:

**表格–学生 _ 详情:**

| [Student id] | 【 name 】 | [mark] |
| --- | --- | --- |
|  |

```sql
SELECT RPAD(Name, 15, "#") AS RightPadStudentName
FROM Student_Details;
```

**输出:**

| [Right Student Name] |
| --- |
| 【麦田里的守望者】【T11】 |