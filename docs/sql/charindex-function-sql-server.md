# CHARINDEX()函数 SQL Server

> 原文:[https://www . geesforgeks . org/charindex-function-SQL-server/](https://www.geeksforgeeks.org/charindex-function-sql-server/)

**CHARINDEX():**
SQL Server 中的这个函数有助于返回给定字符串中子字符串的位置。此函数中执行的搜索不区分大小写。

**语法:**

```sql
CHARINDEX(substring, string, [starting_position]
```

**参数:**
该功能接受 3 个参数。

1.  **子串–**
    我们正在搜索的子串。它有 8000 个字符的限制。
2.  **字符串–**
    进行搜索的字符串。
3.  **起始位置–**
    开始搜索的位置。这是一个可选参数。

**返回:**

*   该函数将返回给定字符串中子字符串的位置。
*   如果在字符串中找不到子字符串，则函数将返回 0。

**适用于以下版本:**

*   SQL Server 2017
*   SQL Server 2016
*   SQL Server 2014
*   SQL Server 2012
*   2008
*   SQL Server 2008
*   SQL Server 2005

**示例-1 :**
使用 CHARINDEX()函数搜索字符。

```sql
SELECT CHARINDEX('k', 'GeeksforGeeks') 
As Found ;
```

**输出:**

| 找到 |
| four |

**示例-2 :**
使用 CHARINDEX()函数搜索子串。

```sql
SELECT CHARINDEX('fully', 'Life is a journey so live it fully') 
As Found ;
```

**输出:**

| 找到 |
| Thirty |

**示例-3 :**
如果子字符串与给定的字符串不匹配。

```sql
SELECT CHARINDEX
('python', 'Geeks for geeks is a well known computer science website') 
As Found ;
```

**输出:**

| 找到 |
| Zero |

**示例-4 :**
在 CHARINDEX()函数中使用“starting _ position”参数。

```sql
SELECT CHARINDEX
('for', 'Love for all, Hate for none', 10) 
As Found ;
```

**输出:**

| 找到 |
| Twenty |

**示例-5 :**
显示 CHARINDEX()函数不区分大小写。

```sql
SELECT  
CHARINDEX('Bear', 'Bob likes Bear, beer likes bob') 
As Found1,
CHARINDEX('bear', 'Bob likes Bear, beer likes bob') 
As Found2 ;
```

**输出:**

| Found1 | Found2 |
| Eleven | Eleven |

**示例-6 :**
使用 COLLATE 子句使函数区分大小写。

```sql
SELECT CHARINDEX
('A', 'There is always a need to Develop' COLLATE Latin1_General_CS_AS) 
As Found;
```

**输出:**
该函数现在遵循区分大小写的搜索，并且由于它不包含“A”，因此该函数将返回 0。

| 找到 |
| Zero |