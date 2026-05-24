# SQL Server 中的 LOG10()函数

> 原文:[https://www.geeksforgeeks.org/log10-function-in-sql-server/](https://www.geeksforgeeks.org/log10-function-in-sql-server/)

这个函数返回以 10 为底的数字的对数。

**语法:**

```sql
LOG10(number)

```

**参数:**
该方法接受如上所述的单参数，如下所述。

*   **数字–**
    该参数保存一个大于 0 的数字。

**返回–**
返回指定数字的以 10 为底的对数。

让我们考虑下面的例子。
**例-1 :**

```sql
SELECT LOG10(1) Result;

```

**输出:**

```sql
Result
0

```

**示例-2 :**

```sql
SELECT LOG10(10) Result;

```

**输出:**

```sql
Result
1

```

**示例-3 :**
返回 10 的以 10 为底的对数。

```sql
SELECT LOG10(10);

```

**输出:**

```sql
1.0

```

**示例-4 :**
返回 1 的以 10 为底的对数。

```sql
SELECT LOG10(1);

```

**输出:**

```sql
0.0

```

**例-5 :**
当参数作为表达式传递时。

```sql
SELECT LOG10(2 * 3);

```

**输出:**

```sql
0.77815125038364363

```