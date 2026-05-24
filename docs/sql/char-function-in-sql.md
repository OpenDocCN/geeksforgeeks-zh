# SQL 中的 CHAR()函数

> 原文:[https://www.geeksforgeeks.org/char-function-in-sql/](https://www.geeksforgeeks.org/char-function-in-sql/)

**CHAR() :**
这个函数可以用来查找基于 ASCII(美国信息交换标准代码)代码的字符。 **CHAR()** 函数不支持多个整数作为参数。

**语法:**

```sql
SELECT CHAR(code);

```

**注意–**
参数代码是必需的，代码的计算结果为 0 到 255 之间的整数值。

**示例-1:**

```sql
SELECT CHAR(65) AS Result;

```

**输出:**

| 结果 |
| --- |
| A |

**示例-2:**

```sql
SELECT CHAR(165) AS Result;

```

**输出:**

| 结果 |
| --- |
| `¥` |

**示例-3:**

```sql
SELECT CHAR(67, 255) AS Result;

```

**输出:**
char 函数需要 1 个参数。如上例所示，当提供多个整数时，它会得到一个错误。

**示例-4:**

```sql
SELECT CHAR(1000) AS Result;

```

**输出:**

| 结果 |
| --- |
| 空 |

**注意–**
上面的示例导致 NULL，因为输入超出了 0 到 255 的范围。

**示例-5:**

```sql
SELECT 'Hello' + CHAR(10) + 'World' AS Result;

```

**输出:**

| 结果 |
| --- |
| 你好 |
| 世界 |

**注意–**
在上面的例子中，CHAR(10)返回新行，因此，第二个字符串放在新行中。