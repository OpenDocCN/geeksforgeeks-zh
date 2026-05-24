# MS 访问中的时间值()和时间序列()函数

> 原文:[https://www . geesforgeks . org/time value-and-time serial-function in-ms-access/](https://www.geeksforgeeks.org/timevalue-and-timeserial-function-in-ms-access/)

**1。时间值()函数:**
在 MS Access 中，时间值()函数根据给定的字符串返回时间。在此函数中，字符串将作为参数传递，并将基于字符串返回时间。返回时间的小时部分是 0 到 12，分钟和秒部分是 0 到 59。

**语法:**

```sql
TimeValue(string)

```

**参数值:**

| 参数 | 描述 |
| 线 | 它是必需的。字符串可以在(00:00:00)到(23:59:59)的范围内 |

**示例-1 :**

```sql
SELECT TimeValue("18:15:38");

```

**输出:**

```sql
6:15:38 PM 

```

**示例-2 :**

```sql
SELECT TimeValue("5:45:18 PM");

```

**输出:**

```sql
5:45:18 PM 

```

**2。TimeSerial()函数:**
在 MS Access 中，TimeSerial()函数返回指定部分的时间。第一部分是小时，第二部分是分钟，第三部分是秒钟。小时在 0 到 23 之间，分钟在 0 到 59 之间，秒在 0 到 59 之间。在这个函数中，将传递带有分隔栏的小时、分钟和秒，并返回时间。

**语法:**

```sql
TimeSerial(hour, minute, second)

```

**参数值:**

| 参数 | 描述 |
| 小时 | 必需的。它将在 0 到 23 的范围内。 |
| 分钟 | 必需的。它将在 0 到 59 的范围内。 |
| 第二 | 必需的。它将在 0 到 59 的范围内。 |

**示例-1 :**

```sql
SELECT TimeSerial(5, 10, 20);

```

**输出:**

```sql
5:10:20 AM 

```

**示例-2 :**

```sql
SELECT TimeSerial(18-4, 49-24, 18-5);

```

**输出:**

```sql
2:25:13 PM 

```