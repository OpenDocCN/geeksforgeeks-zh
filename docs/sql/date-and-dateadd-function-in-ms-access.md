# MS Access 中的日期()和日期添加()功能

> 原文:[https://www . geesforgeks . org/date-and-date add-function-in-ms-access/](https://www.geeksforgeeks.org/date-and-dateadd-function-in-ms-access/)

**1。Date()函数:**
Date()函数返回系统当前日期。在这个函数中，不会传递任何参数，它将返回当前日期。

**语法:**

```sql
Date() 
```

**示例:**

```sql
SELECT Date() AS CurrentDate;
```

**输出–**

| 电流日期 |
| 9/2/2020 |

**2。DateAdd()函数:**
DateAdd()函数将时间间隔和日期添加到给定日期并返回。在这个函数中，第一个参数是间隔符号，第二个参数是要添加的数字，第三个参数是日期，

| 间隔 | 描述 |
| yyyy | 年 |
| q | 四分之一 |
| m | 月 |
| y | 一年中的某一天 |
| d | 一天 |
| w | 工作日 |
| （同 whitewater）白水 | 周 |
| h | 小时 |
| n | 分钟 |
| s | 第二 |

**语法:**

```sql
DateAdd(interval, number, date) 
```

**示例-1 :**

```sql
SELECT DateAdd("yyyy", 3, #02/09/2020#);
```

**输出–**

| **输出:** |
| 2/9/2023 |

**示例-2 :**

```sql
SELECT DateAdd("m", 3, Date()) As Date;
```

**输出–**

| **输出:** |
| 12/2/2020 |