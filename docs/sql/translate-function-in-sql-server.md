# SQL Server 中的 TRANSLATE()函数

> 原文:[https://www . geesforgeks . org/translate-function-in-SQL-server/](https://www.geeksforgeeks.org/translate-function-in-sql-server/)

**TRANSLATE()函数:**
SQL Server 中的这个函数用来返回这个函数的第一个参数中所述字符串的翻译后的字符串，当上面函数的 characters 参数中所述的字符被转换成最后一个参数中所述的字符时，即翻译。

**特征:**

*   当字符参数中给出的字符被转换为最后一个参数中给出的字符时，即翻译时，该函数用于查找第一个参数中所述字符串的修改字符串。
*   该函数接受字符串、字符和翻译作为参数。
*   这个函数可以完全翻译字符串，也可以部分翻译字符串。
*   如果指定的字符和翻译长度不同，此函数会返回错误。

**语法:**

```sql
TRANSLATE(string, characters, translations)
```

**参数:**
该方法接受如下三个参数:

*   **字符串:**指定要翻译的输入字符串。
*   **字符:**必须替换的指定字符。
*   **翻译:**指定新字符。

**返回:**
当字符参数中给定的字符被解释为最后一个参数中所述的字符时，即翻译时，返回该函数第一个参数中所述的字符串的修改后的字符串。

**示例-1 :**
从指定的字符串、字符和翻译中获取字符串。

```sql
SELECT TRANSLATE('Geek', 'Geek', 'geek');
```

**输出:**

```sql
geek
```

**示例-2 :**
使用带有变量的 TRANSLATE()函数，并获取翻译后的字符串作为输出。

```sql
DECLARE @str VARCHAR(2);
SET @str = 'gf';
SELECT TRANSLATE(@str, 'gf', 'cs');
```

**输出:**

```sql
cs
```

**示例-3 :**
使用带有三个变量的 TRANSLATE()函数，获取翻译后的字符串作为输出。

```sql
DECLARE @str VARCHAR(3);
DECLARE @chars VARCHAR(3);
DECLARE @newchar VARCHAR(3);
SET @str = 'abc';
SET @chars = 'ab';
SET @newchar = 'ed';
SELECT TRANSLATE(@str, @chars, @newchar);
```

**输出:**

```sql
edc
```

**示例-4 :**
获取第一个参数中所述字符串的翻译字符串，此时该函数的*字符*参数中给出的字符被解释为最后一个参数中给出的字符，即翻译。

```sql
SELECT TRANSLATE('x*[y+z]/[x-y]', '[][]', '()()');
```

**输出:**

```sql
x*(y+z)/(x-y)
```

**应用:**
当字符参数中给出的字符被解释为最后一个参数中给出的字符时，即翻译时，该函数用于返回第一个参数中所述字符串的翻译字符串。