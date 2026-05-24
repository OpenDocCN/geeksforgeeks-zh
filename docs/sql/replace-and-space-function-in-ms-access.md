# 替换 MS 访问中的()和 Space()功能

> 原文:[https://www . geesforgeks . org/replace-and-space-function-in-ms-access/](https://www.geeksforgeeks.org/replace-and-space-function-in-ms-access/)

**1。Replace()函数:**
在 MS Access 中，Replace 函数会将一个子串替换为另一个带有指定数字的子串。在这个函数中，第一个参数将是字符串，第二个参数将被找到(在字符串中搜索的子字符串)，第三个参数将是替换(在字符串中替换查找的子字符串)，第四个参数是可选的，是起点。如果没有给定，则默认为 1，第五个参数是计数(要执行的替换次数)，这也是可选的。

**语法:**

```sql
Replace(string1, find, replacement, start, count) 
```

**示例–**

```sql
SELECT Replace("geeksforgeeks", "e", "i") AS ReplaceString;
```

**输出–**

| **替换字符串** |
| giiksforgiiks |

**示例–**

```sql
SELECT Replace("geeksforgeeks", "g", "z", 4) AS ReplaceString;
```

**输出–**

| **替换字符串** |
| 极客们 |

**2。Space()函数:**
在 MS Access 中，Space 函数返回给定数量的空格字符的字符串。一个数字将作为参数传递，它将返回一个给定数字长度的字符串，所有字符都是空格。

**语法:**

```sql
Space(number) 
```

**示例–**

```sql
SELECT len(Space(15)) AS SpaceString;
```

**输出–**

| **太空弦** |
| Fifteen |

**示例–**

```sql
SELECT len(Space(10)) AS SpaceString;
```

**输出–**

| **太空弦** |
| Ten |