# 马里亚数据库中的 LPAD、LOWER 和 LTRIM 功能

> 原文:[https://www . geesforgeks . org/lpad-lower-and-ltrim-function-in-mariadb/](https://www.geeksforgeeks.org/lpad-lower-and-ltrim-function-in-mariadb/)

**1。LPAD 函数:**
在马里亚数据库中，LPAD 函数用于用给定长度的指定字符串左填充的字符串。在这个函数中，第一个参数是字符串，第二个参数是长度，第三个参数是填充字符串。

如果字符串长度大于给定的长度，那么它将从字符串中删除字符，以将其缩短为字符长度，否则它将从左边填充字符串。

**语法:**

```sql
LPAD( string, length, pad_string )

```

**示例-1 :**

```sql
SELECT LPAD('geeksforgeeks', 15, 'A');

```

**输出:**

```sql
AAgeeksforgeeks

```

**示例-2 :**

```sql
SELECT LPAD('Computer', 4, 'x');

```

**输出:**

```sql
Comp
```

**示例-3 :**

```sql
SELECT LPAD('DSA', 4, 'gfg');

```

**输出:**

```sql
gDSA
```

**2。低函数:**
在马里亚数据库中，低函数用于将指定字符串中的所有字符转换为小写。第一个参数是字符串。它将返回该字符串的小写字母。如果字符串的字符不是字母，那么这些字符不会受到影响。它的工作原理类似于 LCASE 函数。

**语法:**

```sql
LOWER( string )

```

**示例-1 :**

```sql
SELECT LOWER('GFG');
```

**输出:**

```sql
gfg
```

**示例-2 :**

```sql
SELECT LOWER('GeeksForGeeks');
```

**输出:**

```sql
geeksforgeeks
```

**示例-3 :**

```sql
SELECT LOWER('DSA@SELF!');
```

**输出:**

```sql
dsa@self!
```

**3。LTRIM 函数:**
在马里亚数据库中，LTRIM 函数用于删除字符串左侧的所有空格字符。在这个函数中，一个字符串将作为参数传递，它将返回字符串开头的零空格。如果字符串的右端也包含空格，那么这个函数对此没有任何影响。

**语法:**

```sql
LTRIM( string )
```

**示例-1 :**

```sql
SELECT LTRIM('   geeksforgeeks');
```

**输出:**

```sql
'geeksforgeeks'
```

**示例-2 :**

```sql
ELECT LTRIM('   gfg  ');
```

**输出:**

```sql
'gfg  '
```

**示例-3 :**

```sql
SELECT LTRIM('This is best portal  ');
```

**输出:**

```sql
'This is best portal  '
```