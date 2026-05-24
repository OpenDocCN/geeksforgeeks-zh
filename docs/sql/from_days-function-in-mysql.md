# MySQL 中的 FROM_DAYS()函数

> 原文:[https://www.geeksforgeeks.org/from_days-function-in-mysql/](https://www.geeksforgeeks.org/from_days-function-in-mysql/)

**FROM_DAYS() :**

此函数用于从指定的数字日期值返回日期。这里指定的日期值除以 365，相应地返回年、月和日。此函数仅用于公历中的日期。

**功能:**

*   This function is used to find the date from the specified numeric date value.
*   This function accepts a single parameter.
*   The parameter accepted here is the specified digital day to be converted into a date.
*   This function is only used for dates in the Gregorian calendar.

**语法:**

```sql
FROM_DAYS(number)
```

**参数:**

该函数只接受一个参数。

*   **Number–** Specifies the digital day to be converted into a date.

**返回:**

它从指定的数字日期值返回一个日期。

**示例-1 :**

从指定的数字日期值“366”中获取公历中的日期“0001-01-01”。这里，指定的日期值 366 除以 365，余数为 1，因此返回的年份是 1 月 1 日的 0001。

```sql
SELECT FROM_DAYS(366);
```

**输出:**

```sql
0001-01-01
```

**示例-2 :**

从 366 到 400 之间的随机数字日期值中获取公历中的日期“0001-01-15”。

在这里，为了获取参数日期值，使用了 FLOOR()函数，该函数将返回 366 到 400 之间的日期值。然后使用这个返回的日期值，FROM_DAYS()函数将返回“0001-01-15”的日期。

```sql
SELECT FROM_DAYS(FLOOR(366 + RAND()*(400 - 366 + 1)));
```

**输出:**

```sql
0001-01-15
```

**示例-3 :**

从数字日期值“1000”中获取公历中的日期“0002-09-27”。在这里，日期值“1000”从 POWER()函数返回，然后 FROM_DAYS()函数将该值作为参数，并返回日期“0002-09-27”。

```sql
SELECT FROM_DAYS(POWER(10, 3));
```

**输出:**

```sql
0002-09-27
```

**示例-4 :**

从数字日期值“432.2”中获取公历中的日期“0001-03-08”。这里的日期值“432.2”是由 ABS()函数返回的“-432.2”的绝对值。返回的绝对值“432.2”作为 FROM_DAYS()函数的参数，该函数给出日期“0001-03-08”作为返回值。

```sql
SELECT FROM_DAYS(ABS(-432.2));
```

**输出:**

```sql
0001-03-08
```

**应用:**

此函数用于从指定的数字日期值返回日期。