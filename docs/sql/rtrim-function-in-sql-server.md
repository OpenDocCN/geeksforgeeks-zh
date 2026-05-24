# SQL Server 中的 RTRIM()函数

> 原文:[https://www.geeksforgeeks.org/rtrim-function-in-sql-server/](https://www.geeksforgeeks.org/rtrim-function-in-sql-server/)

函数的作用是:从字符串中删除尾随空格。

**语法:**

```sql
RTRIM(input_string)

```

**参数:**
RTRIM()函数接受 input_string 这样的单参数。

*   **input_string :**
    它是一个字符或二进制数据的表达式。它可以是文字字符串、变量或列。

**返回–**截断所有尾随空格后返回一个字符串。

**示例-1 :**
使用带有文字字符串的 RTRIM()函数。

```sql
SELECT RTRIM('GFG a computer science portal for geeks') 
AS RightTrimmedString;

```

**输出:**

<figure class="table">

| 右试字符串 |
| GFG is a computer science portal for geeks. |

</figure>

**示例-2 :**
使用带有变量的 RTRIM()函数。

```sql
DECLARE @input_string varchar(25);  
SET @input_string = 'IPL sponsorship this year.';  
SELECT RTRIM(@input_string) + ' Dream11  '; 

```

**输出:**

```sql
IPL sponsorship this year Dream11

```

**示例-3 :**
您可以使用带有问答变量的 RTRIM()函数，如下例所示。

```sql
DECLARE @input_string varchar(25);  
SET @input_string = 'who is the sponsor for IPL Game this year :';  
SELECT RTRIM(@input_string)+'Dream11' ; 

```

**输出:**

```sql
who is the sponsor for IPL Game this year :Dream11

```