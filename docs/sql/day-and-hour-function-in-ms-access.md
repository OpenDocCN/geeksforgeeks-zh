# MS 接入中的日()和时()功能

> 原文:[https://www . geesforgeks . org/ms-access 中的日和小时功能/](https://www.geeksforgeeks.org/day-and-hour-function-in-ms-access/)

**1。Day()函数:**
Day()函数返回给定日期的月份。在这个函数中，它将日期作为参数，并返回该日期的日期。返回的日期将在 1 点到 31 点之间。

**语法:**

```sql
Day(date)
```

**示例-1 :**

```sql
SELECT Day(#02/23/2020#);
```

**输出–**

```sql
23
```

**示例-2 :**

```sql
SELECT Day(#09/10/2010#);
```

**输出–**

```sql
10
```

**2。Hour()函数:**
Hour()函数返回给定日期时间的小时部分。在这个函数中，日期时间将作为参数传递，并将返回其中的小时部分。返回的小时部分将在 1 到 23 之间。

**语法:**

```sql
Hour(time)
```

**示例-1 :**

```sql
SELECT Hour(#04/10/2020 01:08:24 AM#);
```

**输出–**

```sql
1
```

**示例-2 :**

```sql
SELECT Hour(#12:40:33#);
```

**输出–**

```sql
12
```