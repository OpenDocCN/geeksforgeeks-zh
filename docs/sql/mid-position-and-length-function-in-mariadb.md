# 马里亚数据库中的 MID()，POSITION()和 LENGTH()函数

> 原文:[https://www . geesforgeks . org/Maria db 中位长度函数/](https://www.geeksforgeeks.org/mid-position-and-length-function-in-mariadb/)

**1。MID()函数:**
在马里亚数据库中， **MID()函数**用于从字符串中提取子字符串。它将从起点返回给定长度的子字符串。如果起始位置是正数，那么它将从起始索引开始。如果为负，则从结束索引开始。

**语法:**

```sql
MID(string, start_position, length)
```

**参数:**
该功能接受三个参数，如上所述，描述如下:

*   **字符串–**
    应用了 MID()函数的字符串。
*   **start _ position–**
    要提取的字符串的起始位置。
*   **长度–**
    要提取的字符串的长度。

**返回:**从起点开始给定长度的子串。

**示例-1 :**

```sql
SELECT MID('geeksforgeeks', 1, 4);
```

**输出:**

```sql
geek
```

**示例-2 :**

```sql
SELECT MID('computerscience', 2, 2);
```

**输出:**

```sql
om
```

**例-3 :**

```sql
SELECT MID('algorithm', -3, 3);
```

**输出:**

```sql
him
```

**2。POSITION()函数:**
在马里亚数据库中， **POSITION()函数**用于查找字符串中子串的位置。它将返回字符串中第一个出现的子字符串的位置。如果字符串中不存在子字符串，则它将返回 0。它的工作原理类似于 LOCATE()函数。当在字符串中搜索子字符串的位置时，该函数不执行区分大小写的搜索。

**语法:**

```sql
POSITION(substring IN string)
```

**参数:**该功能接受两个参数，如上所述，描述如下:

*   **子字符串:**要搜索的字符串。
*   **字符串:**执行搜索操作的字符串。

**返回:**字符串中第一个出现的子字符串的位置。

**示例-1 :**

```sql
SELECT POSITION('g' IN 'gfg');
```

**输出:**

```sql
1
```

**示例-2 :**

```sql
SELECT POSITION('s' IN 'DSASELFPACED');
```

**输出:**

```sql
2
```

**例-3 :**

```sql
SELECT POSITION('X' IN 'geeksforgeeks');
```

**输出:**

```sql
0
```

**3。LENGTH()函数:**
在马里亚数据库中， **LENGTH()函数**用于返回指定字符串的长度。它将以字节为单位进行测量。它的工作原理类似于 CHAR_LENGTH 函数。

**语法:**

```sql
LENGTH(string)
```

**参数:**必选。字符串值。
**返回:**输入字符串的长度。

**示例-1 :**

```sql
SELECT LENGTH('geeksforgeeks');
```

**输出:**

```sql
13
```

**示例-2 :**

```sql
SELECT LENGTH('');
```

**输出:**

```sql
0
```

**例-3 :**

```sql
SELECT LENGTH(' ');
```

**输出:**

```sql
1
```