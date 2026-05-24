# MySQL 中的 SUBSTRING_INDEX()函数

> 原文:[https://www . geesforgeks . org/substring _ index-function-in-MySQL/](https://www.geeksforgeeks.org/substring_index-function-in-mysql/)

**SUBSTRING_INDEX** ()函数在 MySQL 中用于返回分隔符出现指定次数之前的字符串中的子字符串。

**语法:**

```sql
SUBSTRING_INDEX( str, delim, count )

```

**参数:**这个方法接受三参数，如上所述，如下所述:

*   **str:** The original string from which we want to create the substring.
*   **Delim:** is a string that acts as a separator. The function performs case-sensitive matching when searching for separators.
*   **Count:** Identifies the number of searches for separators. It can be positive or negative. If it is a positive number, this function returns everything to the left of the separator. If it is negative, this function will return everything to the right of the separator.

**返回**:返回给定字符串的子串。

**示例-1 :** SUBSTRING_INDEX()函数，分隔符出现次数为正数

```sql
SELECT SUBSTRING_INDEX("www.geeksforgeeks.org", ".", 2) as Sub_Str;

```

**输出:**

|  |
| --- |
| www。极客锻造 |

**示例-2 :** SUBSTRING_INDEX()函数，分隔符出现次数为负数。

```sql
SELECT SUBSTRING_INDEX("www.geeksforgeeks.org", ".", -2) as Sub_Str;

```

**输出:**

|  |
| --- |
|  |

**示例-3 :** SUBSTRING_INDEX()函数，带有表数据。

**表:员工:**

| Employee _Id | address |
| --- | --- |
| One hundred and one | 700000 Calcutta W.B. |
| One hundred and two | 75102 Jia Paige Li W.B. |
| One hundred and three | 71101 Midnapol W |

现在，我们将使用 SUBSTRING_INDEX 函数找到每个员工的 pin 号地址。

```sql
SELECT  SUBSTRING_INDEX(Address, '  ', 1 )  AS Pin_Num FROM Employee 

```

**输出:**

| 【pin _ num】 |
| --- |
| 【70000】 |
| 【735102】 |