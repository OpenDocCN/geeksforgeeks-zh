# MySQL 中的 ASCII()函数

> 原文:[https://www.geeksforgeeks.org/ascii-function-in-mysql/](https://www.geeksforgeeks.org/ascii-function-in-mysql/)

在本文中，我们将通过示例介绍 ASCII 函数，您将看到 ASCII MYSQL 查询。还将包括给定字符的 ASCII 码。我们一个一个来讨论。

**ASCII** [函数在 MySQL](https://www.geeksforgeeks.org/sql-functions-aggregate-scalar-functions/) 中用来查找一个字符表达式最左边字符的 ASCII 码。

**语法:**

```sql
ASCII(str)

```

**参数:**
这个方法在语法中接受一个参数，如上面提到的，并在下面的例子中描述。

*   **字符串–**要检索最左边字符的 ASCII 值的字符串。

**返回:**
返回最左边字符的 ASCII 码。如果字符串为空，它也返回 0；如果字符串为空，它返回空。

**示例-1 :**
ASCII()函数检查一个小写字符的值。

```sql
SELECT ASCII('g')AS Lower_Case;

```

**输出:**

| 小写 |
| --- |
| One hundred and three |

**示例-2 :**
ASCII()函数检查大写字符的值。

```sql
SELECT ASCII('G')AS Upper_Case;

```

**输出:**

| 大写 |
| --- |
| Seventy-one |

**示例-3 :**
ASCII()函数检查输入字符串的值。

```sql
SELECT ASCII('MySQL')AS String_Value;

```

**输出:**

| 字符串值 |
| --- |
| Seventy-seven |

**示例-4 :**
ASCII()函数检查表下一列中每个输入字符串的值。

**表格-学生 _ 详情**

| 学生标识 | 学生名 |
| --- | --- |
| One hundred and one | 蒂娜（号外乐团成员） |
| One hundred and two | rohit！rohit |
| One hundred and three | 等于 Haman） |
| One hundred and three | 雪 |

```sql
SELECT ASCII(Student_Name)  AS Ascii_Name FROM Student_Details ;

```

| Ascii _ 名称 |
| --- |
| Eighty-four |
| Eighty-two |
| Sixty-five |
| Eighty-three |