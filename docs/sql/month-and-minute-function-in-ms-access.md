# MS 接入中的月()和分()功能

> 原文:[https://www . geesforgeks . org/月分钟功能 in-ms-access/](https://www.geeksforgeeks.org/month-and-minute-function-in-ms-access/)

**1。Month()函数:**
在 MS Access 中，Month()函数返回给定日期的月份部分。在这个函数中，它将日期作为参数，并返回月份部分。它将返回 0 到 12 之间的整数。

**语法:**

```sql
Month(date)
```

**示例-1 :**

```sql
SELECT Month(#06/11/2020#);
```

**输出–**

```sql
6
```

**示例-2 :**

```sql
SELECT Month(Date());
```

**输出–**

```sql
9
```

**2。分钟()函数:**
在 MS Access 中，分钟()函数返回给定日期时间的分钟部分。在此函数中，日期时间将作为参数传递，并将返回分钟部分。它将返回 0 到 59 之间的整数。

**语法:**

```sql
Minute(time)
```

**示例-1 :**

```sql
SELECT Minute(#04/12/2020 10:14:34 PM#);
```

**输出–**

```sql
14
```

**示例-2 :**

```sql
 SELECT Minute(#09:03:07#);
```

**输出–**

```sql
3
```