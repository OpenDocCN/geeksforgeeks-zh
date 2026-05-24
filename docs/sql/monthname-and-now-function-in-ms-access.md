# MS Access 中的 MonthName()和 Now()功能

> 原文:[https://www . geesforgeks . org/monthname-and-now-function-in-ms-access/](https://www.geeksforgeeks.org/monthname-and-now-function-in-ms-access/)

**1。MonthName()函数:**
MonthName()函数根据数字返回月份名称。在这个函数中，第一个参数是月号，第二个参数是缩写。它将是可选的。如果我们将通过缩写为真，那么月名应该缩写，否则不。如果我们没有在缩写的地方传递任何值，那么默认情况下它是假的。一月是第一个月，十二月是第十二个月。

**语法:**

```sql
MonthName(number, abbreviate) 
```

**示例-1 :**

```sql
SELECT MonthName(7);
```

**输出–**

```sql
July
```

**示例-2 :**

```sql
SELECT MonthName(3, FALSE);
```

**输出–**

```sql
Mar
```

**2。Now()函数:**
Now()函数返回计算机系统当前的日期和时间。在这个函数中，没有参数会通过它返回当前的日期时间。

**语法:**

```sql
Now()
```

**示例:**

```sql
SELECT Now();
```

**输出–**

```sql
9/3/2020 2:10:29 AM
```