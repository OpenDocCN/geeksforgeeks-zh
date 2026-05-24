# 马里亚数据库中的 TO_DAYS 函数和 WEEK 函数

> 原文:[https://www . geesforgeks . org/to _ days-function-week-function-in-mariadb/](https://www.geeksforgeeks.org/to_days-function-and-week-function-in-mariadb/)

**TO_DAYS 函数:**
在马里亚数据库中，TO_DAYS 函数将日期转换为数字日。在这个函数中，第一个参数是日期。该函数返回日期的数字日。此功能仅适用于公历中的日期。如果日期为“0000-00-00”，此函数将返回空值。它与 FROM_DAYS 函数相反。

**语法:**

```sql
TO_DAYS( date )

```

**参数:**

<figure class="table">

| parameter | explain |
| date | Date to be converted into digital day. |

</figure>

**返回:**
将日期返回为数字日。

**示例-1 :**

```sql
SELECT TO_DAYS('2014-11-20');

```

**输出:**

```sql
735922

```

**示例-2 :**

```sql
SELECT TO_DAYS('2014-11-18 05:30:00');

```

**输出:**

```sql
735920

```

**示例-3 :**

```sql
SELECT TO_DAYS('0000-00-00');

```

**输出:**

```sql
NULL
```

**周函数:**
在马里亚数据库中，周函数用于返回日期值的周部分。在这个函数中，第一个参数是日期值，第二个参数是模式。根据指定的模式，此函数将返回 0-53 或 1-53 之间的值。该函数返回的结果与 WEEK 函数相同，语法为 WEEK(date_value，3)。

**语法:**

```sql
WEEK( date_value, [ mode ] )

```

**参数:**

<figure class="table">

| parameter | describe |
| Date value | From which to extract the date or datetime value of the week. |
| model | Optional. It is used to specify the start date of the week. |

</figure>

**返回:**
返回日期值的周部分。

**示例:**

```sql
SELECT WEEK('2020-01-05');

```

**输出:**

```sql
1
```