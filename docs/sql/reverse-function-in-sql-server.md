# SQL Server 中的 REVERSE()函数

> 原文:[https://www . geesforgeks . org/reverse-function-in-SQL-server/](https://www.geeksforgeeks.org/reverse-function-in-sql-server/)

**REVERSE()函数:**
SQL Server 中的这个函数是用来对所述字符串进行反转并返回输出的。

**特征:**

*   该函数用于反转所述字符串。
*   该函数接受字符串作为参数。
*   这个函数总是返回字符串。
*   这个函数也可以取一组整数并反转它。
*   这个函数甚至可以反转浮点值。

**语法:**

```sql
REVERSE(string)
```

**参数:**
该方法只接受一个参数，如下所示:

*   **字符串:**指定要反转的字符串。

**返回:**
以相反的形式返回指定的字符串。

**示例-1 :**
获取指定字符串的反转字符串。

```sql
SELECT REVERSE('gfG');
```

**输出:**

```sql
Gfg
```

**示例-2 :**
使用带有变量的 REVERSE()函数，获取指定字符串的 REVERSE 字符串。

```sql
DECLARE @string VARCHAR(15);  
SET @string = 'geeksforGeeks';  
SELECT REVERSE(@string);

```

**输出:**

```sql
skeeGrofskeeg
```

**示例-3 :**
获取一组整数的反串。

```sql
SELECT REVERSE(123);
```

**输出:**

```sql
321
```

**示例-4 :**
获取浮点值的反向字符串。

```sql
SELECT REVERSE(1.56);
```

**输出:**

```sql
65.1
```

**应用:**
此函数用于反转指定的字符串，然后将其作为输出返回。