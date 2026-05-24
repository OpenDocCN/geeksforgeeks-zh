# MySQL 中的 MAKETIME()函数

> 原文:[https://www.geeksforgeeks.org/maketime-function-in-mysql/](https://www.geeksforgeeks.org/maketime-function-in-mysql/)

**MAKETIME()函数:**
[MySQL](https://www.geeksforgeeks.org/sql-tutorial/)中的这个函数用于根据指定的小时、分钟和秒值创建并返回时间值。在 MySQL 中，时间值限制是 838:59:59。

**语法:**

```sql
MAKETIME(hour, minute, second)
```

**参数:**
该方法接受如下三个参数–

*   **小时:**指定小时值
*   **分钟:**指定分钟值
*   **秒:**指定秒值

**返回:**
根据指定的时、分、秒值返回时间值。

**示例-1 :**
从指定的 9 小时 3 分 12 秒获取时间“09:03:12”。

```sql
SELECT MAKETIME(9, 3, 12);
```

**输出:**

```sql
09:03:12
```

**示例-2 :**
从指定的 838 小时 54 分 59 秒获取时间“838:54:59”。

```sql
SELECT MAKETIME(838, 54, 59);
```

**输出:**

```sql
838:54:59
```

**示例-3 :**
从指定的 839 小时 12 分 9 秒获取时间“838:59:59”。这里的小时数为 839，大于 838 的小时数限制，因此返回的时间达到其“838:59:59”的限制。

```sql
SELECT MAKETIME(839, 12, 9);
```

**输出:**

```sql
838:59:59
```

**应用:**
该函数用于根据指定的小时、分钟和秒值创建并返回时间值。