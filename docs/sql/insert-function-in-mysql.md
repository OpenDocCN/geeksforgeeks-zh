# MySQL 中的 INSERT()函数

> 原文:[https://www.geeksforgeeks.org/insert-function-in-mysql/](https://www.geeksforgeeks.org/insert-function-in-mysql/)

**INSERT():**
MySQL 中的这个函数用于在字符串中插入一个字符串，从原始字符串中删除一些字符。

**语法:**

```sql
INSERT(str, pos, len, newstr)
```

**参数:**
该方法接受四个参数。

*   **字符串–**我们要在其中插入另一个字符串的原始字符串。
*   **位置–**我们要插入另一个字符串的位置。
*   **len–**要替换的字符数。
*   **newstr–**要插入的字符串。

**返回:**
返回一个新形成的字符串。
**示例-1 :**
将字符串“mysql”插入字符串“geeksforgeeks”并替换五个字符，从位置 9 开始，借助 INSERT Function。

```sql
SELECT INSERT("geeksforgeeks", 9, 5, "MySQL") 
AS NewString ;
```

**输出:**

| 新字符串 |
| --- |
| geeksformysql |

**示例-2 :**
下面的 MySQL 语句返回 Original 字符串，实际的字符串本身。发生这种情况是因为指定为-5 的插入位置超出范围，因此不会发生插入。

```sql
SELECT INSERT("geeksforgeeks", -5, 5, "MySQL") 
AS NewString ;
```

**输出:**

| 新字符串 |
| --- |
| 极客们 |

**示例-3 :**
下面的 MySQL 语句返回了一个全新的字符串。这是因为插入位置是 1，长度是前一个字符串中的字符数。

```sql
SELECT INSERT("geeksforgeeks", 1, 13, "stackoverflow") 
AS NewString ;
```

**输出:**

| 新字符串 |
| --- |
| 堆栈溢出 |