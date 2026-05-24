# MySQL 中的 SUBSTRING()函数

> 原文:[https://www.geeksforgeeks.org/substring-function-in-mysql/](https://www.geeksforgeeks.org/substring-function-in-mysql/)

**SUBSTRING() :**
[函数在 MySQL 中](https://www.geeksforgeeks.org/sql-functions-aggregate-scalar-functions/)用来从任意给定的字符串中派生出子串。它从输入字符串中的给定位置开始提取指定长度的字符串。子字符串的目的是返回字符串的特定部分。

**语法:**

```sql
SUBSTRING(string, start, length)
OR
SUBSTRING(string FROM start FOR length)

```

**参数:**
该方法接受三参数，如上所述，如下所述。

*   **字符串–**
    输入要从中提取的字符串。
*   **开始–**
    开始位置。如果是正数，这个函数从字符串的开头提取。如果是负数，这个函数从字符串的末尾提取。
*   **长度–**
    可选。它标识要提取的字符数。如果没有给定，则整个字符串从起始位置返回。

**示例-1 :**
从给定的字符串中导出子字符串，而不给出长度参数。

```sql
SELECT SUBSTRING("GeeksForGeeks", 3) AS Sub_String;

```

**输出:**

<center>

| 子字符串 |
| --- |
| eksForGeeks |

</center>

**示例-2 :**
在给定长度参数的情况下，从给定字符串中导出子字符串。

```sql
SELECT SUBSTRING("GeeksForGeeks", 3, 8) AS Sub_String; 

```

**输出:**

<center>

| 子字符串 |
| --- |
| eksForGe |

</center>

**示例-3 :**
当起始位置为-ve 时，从给定的字符串派生子字符串，即:从结束开始。

```sql

SELECT SUBSTRING("GeeksForGeeks", -3 ) AS Sub_String; 

```

**输出:**

<center>

| 子字符串 |
| --- |
| eks |

</center>

**示例-4 :**
从表中的文本列提取所有子串。

**表:**学生 _ 详细信息

<center>

| 学生标识 | 学生名 |
| --- | --- |
| One hundred and one | 维拉特 |
| One hundred and two | rohit！rohit |
| One hundred and three | Rahul |
| One hundred and four | shikhar |

</center>

```sql
SELECT SUBSTRING( Student_Name, 2 ) AS Sub_String FROM Student_Details ;

```

**输出:**

<center>

| 子字符串 |
| --- |
| irat |
| 你完了 |
| 啊啊啊啊啊啊啊啊啊啊啊啊啊啊啊啊啊啊啊啊啊啊啊啊啊啊啊啊啊啊啊啊啊啊啊啊啊啊啊 |
| ikhar |

</center>