# MySQL 中的 FIND_IN_SET()函数

> 原文:[https://www . geesforgeks . org/find _ in _ set-function-in-MySQL/](https://www.geeksforgeeks.org/find_in_set-function-in-mysql/)

**FIND_IN_SET()** 函数用于查找字符串在字符串列表中的位置。如果字符串重复多次，输出将是该字符串的第一个位置。

**注意点:**

*   如果在字符串列表中找不到字符串，则结果为 0
*   如果字符串或字符串列表为空，则结果为空
*   如果 string_list 是空字符串("")，则结果为 0

**语法:**

```sql
FIND_IN_SET("string", "string_list")
```

**注意:**参数**字符串**是搜索**字符串 _list 的必选项；** string_list 是字符串值的列表。

**示例-1:**
在字符串列表中搜索“a”:

```sql
SELECT FIND_IN_SET("a", "g, e, e, k, s, f, o, r, g, e, e, k, s"); 
```

**结果–**

| FIND_IN_SET("a "，" geeksforgeeks ") |
| --- |
| Zero |

**示例-2:**
在字符串列表中搜索“q”(字符串列表为空) :

```sql
SELECT FIND_IN_SET("a", null); 
```

**结果–**

| 查找输入设置(“一”，空) |
| --- |
| 空 |

**示例-3:**
在字符串列表中搜索“q”:

```sql
SELECT FIND_IN_SET("g", "g, e, e, k, s, f, o, r, g, e, e, k, s"); 
```

**结果–**

| FIND_IN_SET("g "，" g，e，e，k，s，f，o，r，g，e，k，s ") |
| --- |
| one |