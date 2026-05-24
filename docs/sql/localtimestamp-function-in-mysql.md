# MySQL 中的 LOCALTIMESTAMP()函数

> 原文:[https://www . geesforgeks . org/local timestamp-function-in-MySQL/](https://www.geeksforgeeks.org/localtimestamp-function-in-mysql/)

**LOCALTIMESTAMP()函数:**
这个函数在 MySQL 中是用来以“YYYY-MM-DD HH-MM-SS”(字符串)或者以 YYYYMMDDHHMMSS.uuuuuu(数字)的格式返回当前日期和时间的。

**语法:**

```sql
LOCALTIMESTAMP
OR
LOCALTIMESTAMP()
```

**参数:**
此方法不接受任何参数。

**返回:**
返回当前日期和时间。

**例-1 :**
以“YYYY-MM-DD HH-MM-SS”格式获取当前日期时间“2020-11-25 07:57:09”。

```sql
SELECT LOCALTIMESTAMP();
```

**输出:**

```sql
2020-11-25 07:57:09
```

**例-2 :**
获取当前日期时间+ 1 为“20201125075901”，格式为“YYYYMMDDHHMMSS.uuuuuu”。

```sql
SELECT LOCALTIMESTAMP() + 1;
```

**输出:**

```sql
20201125075901

```

**例-3 :**
以“YYYY-MM-DD HH-MM-SS”格式获取当前日期时间“2020-11-25 08:11:55”。

```sql
SELECT LOCALTIMESTAMP as CurrDateTime;
```

**输出:**

```sql
2020-11-25 08:11:55
```

**应用:**
该功能用于返回当前日期和时间。