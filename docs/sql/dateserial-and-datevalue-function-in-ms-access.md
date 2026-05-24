# MS Access 中的日期序列()和日期值()功能

> 原文:[https://www . geesforgeks . org/date serial-and-date value-function-in-ms-access/](https://www.geeksforgeeks.org/dateserial-and-datevalue-function-in-ms-access/)

在本文中，我们将通过示例介绍 MS Access 中的 DateSerial()和 DateValue()函数，并将通过输出介绍 DateSerial 和 DateValue 查询。

**日期序列()函数:**
日期序列函数的格式包含年、月和日三个部分的值。它以指定的格式返回日期。有三个参数，第一个是年，第二个是月，第三个是日。

**语法:**

```sql
DateSerial(year, month, day)

```

**参数值:**

| **参数** | **描述** |
| 年 | 这是必需的。它将指定一个 4 位数的年份。 |
| 月 | 这是必需的。它将指定一个 2 位数的月份。 |
| 天 | 这是必需的。它将指定一个 2 位数的日期。 |

**示例-1 :**

```sql
SELECT DateSerial(2020-10, 10-1, 20-5);

```

**输出:**

```sql
9/15/2010 

```

**示例-2 :**

```sql
SELECT DateSerial(2020, 4, 20);

```

**输出:**

```sql
4/20/2020 

```

**DateValue()函数:**
在 MS Access 中，DateValue()函数根据字符串返回日期。在此函数中，将传递一个包含日、月和年的字符串，并根据该字符串返回日期。

**注:**
如果没有给出字符串的年份部分，则取当年。

**语法:**

```sql
DateValue(string_date)

```

**参数值:**

| **参数** | **描述** |
| 字符串 _ 日期 | 这是必需的。它将代表从 100 年 1 月 1 日到 9999 年 12 月 31 日的日期。 |

**示例-1 :**

```sql
SELECT DateValue("May 12, 2010");

```

**输出:**

```sql
5/12/2010

```

**示例-2 :**

```sql
SELECT DateValue("July 10");

```

**输出:**

```sql
7/10/2020 

```