# MySQL 中的 LEFT()函数

> 原文:[https://www.geeksforgeeks.org/left-function-in-mysql/](https://www.geeksforgeeks.org/left-function-in-mysql/)

**LEFT** ()函数在 MySQL 中用于从给定字符串的左侧提取指定数量的字符。它使用第二个参数来决定应该返回多少个字符。

**语法:**

```sql
LEFT (str, len)
```

**参数:**该函数接受两个参数，如上所述，如下所述:

*   **字符串:**要从其左侧提取多个字符的给定字符串。

*   **len :** 要提取的字符数。如果此参数大于字符串中的字符数，此函数将返回实际字符串。

**返回:**从一个字符串(从左开始)中返回多个字符。

**示例-1 :**
将左()函数应用于给定的字符串。

```sql
SELECT LEFT("geeksforgeeks", 4) AS Left_Str;
```

**输出:**

<figure class="table">

| 左 _ Str |
| --- |
| 极客 |

</figure>

**示例-2 :**
对数字应用左()函数。

```sql
SELECT LEFT(12345678, 4) AS Left_Num;
```

**输出:**

<figure class="table">

| Left _ Num |
| --- |
| One thousand two hundred and thirty-four |

</figure>

**示例-3 :**
在给定字符串中插入>个字符时，对该字符串应用左()函数。

```sql
SELECT LEFT("geeksforgeeks", 20) AS Left_Str;
```

**输出:**

<figure class="table">

| 左 _ Str |
| --- |
| 极客们 |

</figure>

**示例-4 :**
将左()函数应用于表中的列。

**表:**学生 _ 详情

<figure class="table">T13T15T18】阿尼凯特 T20anike1001@gmail.comT23T26】尼廷 T28】nitin5438@yahoo.com【T29

| Student _Id | Student _ name | Student _ email |
| --- | --- | --- |
| One million six hundred and ten thousand one hundred and ten | One million six hundred and ten thousand one hundred and eleven |

</figure>

```sql
SELECT Student_Name, LEFT(Student_Email, 9) AS Email_Name 
FROM Student_Details;
```

**输出:**

<figure class="table">

|  | [Student name] | [e-mail name] |
| --- | --- | --- |

</figure>