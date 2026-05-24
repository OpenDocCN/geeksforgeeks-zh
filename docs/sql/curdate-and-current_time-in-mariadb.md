# 马里亚数据库中的 CURRENT_TIME()和 CURRENT _ TIME()

> 原文:[https://www . geesforgeks . org/curate-and-current _ time-in-Maria db/](https://www.geeksforgeeks.org/curdate-and-current_time-in-mariadb/)

在本文中，我们将讨论 CURDATE 和 CURRENT_TIME 函数，同时，我们将通过一个例子来了解这两个函数的工作原理。

**1。
在马里亚数据库中，可达函数用于返回当前日期。在这个函数中，不会传递任何参数。该函数将返回当前日期。该函数的工作方式类似于 CODETATE 函数。如果在字符串上下文中使用。那么它将以“YYYY-MM-DD”格式返回当前日期。如果在数字上下文中使用。那么它将以 YYYMMDD 格式返回当前日期。**

**语法:**

```sql
CURDATE( )
```

**参数:**
不会为 CODETATE 函数传递任何参数或自变量。

**示例-1 :**

```sql
SELECT CURDATE();
```

**输出:**

```sql
'2020-10-17'
```

**示例-2 :**

```sql
SELECT CURDATE() + 0;
```

**输出:**

```sql
20201017
```

**示例-3 :**

```sql
SELECT CURDATE() + 2;
```

**输出:**

```sql
20201019
```

**2。当前时间:**
在马里亚数据库中，当前时间函数用于返回当前时间。在这个函数中，不会传递任何参数。该函数将返回当前时间。该函数的工作方式类似于 CURTIME 函数。如果在字符串上下文中使用。那么它将以“时:分:秒”的格式返回当前时间。如果在数字上下文中使用。那么它将以 HHMMSS 格式返回当前时间。

**语法:**

```sql
CURRENT_TIME( )
```

**参数:**
不会为 CURRENT_TIME 函数传递任何参数或自变量。

**示例-1 :**

```sql
SELECT CURRENT_TIME();
```

**输出:**

```sql
'07:25:28'
```

**示例-2 :**

```sql
SELECT CURRENT_TIME()+4;
```

**输出:**

```sql
072532
```

**示例-3 :**

```sql
SELECT CURRENT_TIME()+0;
```

**输出:**

```sql
072528
```