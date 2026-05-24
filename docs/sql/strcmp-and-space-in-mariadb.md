# 马里亚数据库中的 STRCMP()和 SPACE()

> 原文:[https://www.geeksforgeeks.org/strcmp-and-space-in-mariadb/](https://www.geeksforgeeks.org/strcmp-and-space-in-mariadb/)

**1。STRCMP() :**
在马里亚数据库中，STRCMP()函数使用当前字符集测试两个字符串是否相同。在这个函数中，第一个参数是 string1，第二个参数是 string2。如果两个字符串相同，则返回 0，如果第一个字符串大于第二个字符串，则返回 1，如果第二个字符串大于第一个字符串，则返回-1。

**语法:**

```sql
STRCMP( string1, string2 )
```

**参数:**

**String1，string 2–**要相互比较的两个字符串。

**返回:**
它会返回 1，0，-1。

**示例-1 :**

```sql
SELECT STRCMP
('geeksforgeeks', 'geeksforgeeks');
```

**输出:**

```sql
0
```

**示例-2 :**

```sql
SELECT STRCMP('DSA', 'DBMS');

```

**输出:**

```sql
1
```

**示例-3 :**

```sql
SELECT STRCMP('Article', 'Post');

```

**输出:**

```sql
-1
```

**2。SPACE()函数:**
在马里亚数据库中，SPACE()函数返回一个具有指定空格数的字符串。在这个函数中，第一个参数是数字。它将在结果中返回该数量的空格。如果数字为负或 0，则不返回空格。

**语法:**

```sql
SPACE( number )

```

**参数:**
**Number–**
要返回的空格数。

**Return :**
它将返回一个给定数字空间的字符串。

**示例-1 :**

```sql
SELECT SPACE(3);
```

**输出:**

```sql
'   '
```

**示例-2 :**

```sql
SELECT SPACE(0);
```

**输出:**

```sql
''
```

**示例-3 :**

```sql
SELECT SPACE(-5);
```

**输出:**

```sql
''
```