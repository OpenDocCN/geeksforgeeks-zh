# MySQL 中的 INSTR()函数

> 原文:[https://www.geeksforgeeks.org/instr-function-in-mysql/](https://www.geeksforgeeks.org/instr-function-in-mysql/)

**INSTR():**
MySQL 中的这个函数用来返回给定字符串中第一个出现的子字符串的位置。

**语法:**

```sql
INSTR(string_1, string_2)
```

**参数:**
该功能接受 2 个参数。

*   **string _ 1–**
    进行搜索的字符串。
*   **字符串 _ 2–**
    将在字符串 _1 中搜索的字符串/子字符串。

**返回:**
返回给定字符串中第一个出现的子字符串的位置。

**注–**

*   如果在 string_1 中找不到 string_2，函数将返回 0。
*   INSTR()函数只执行不区分大小写的搜索。

**例-1:**
寻找子串的位置。

```sql
SELECT INSTR("Python is a powerful Language", "powerful") 
AS Found;
```

**输出:**

| 找到 |
| Thirteen |

**示例-2:**
显示 INSTR()函数不区分大小写。

```sql
SELECT  
 INSTR("Python is a powerful Language", "IS") 
AS 'Found1';
 INSTR("Python is a powerful Language", "is") 
AS 'Found2';
```

**输出:**

| Found1 | Found2 |
| eight | eight |

**例-3:**
如果在 string_1 中找不到 string_2。

```sql
SELECT INSTR("Python is awesome", "hey") 
AS Found;
```

**输出:**

| 找到 |
| Zero |

**示例-4:**
INSTR()函数中所有可能的错误。
如果只通过一个参数。

```sql
SELECT INSTR("Python is a powerful Language") 
AS 'Found';
```

**输出:**

```sql
Incorrect parameter count in the call to native function 'INSTR'
```

如果传递了三个或更多参数。

```sql
SELECT INSTR("Python is a powerful Language", "is", "a", "lang) 
AS 'Found';
```

**输出:**

```sql
Incorrect parameter count in the call to native function 'INSTR'
```