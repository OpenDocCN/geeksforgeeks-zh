# 马里亚数据库中的季度()和秒 _ 至 _ 时间()

> 原文:[https://www . geesforgeks . org/quart-and-sec _ to-time-in-Maria db/](https://www.geeksforgeeks.org/quarter-and-sec_to_time-in-mariadb/)

**1。季度功能:**

在马里亚数据库中，季度函数返回日期值的季度部分。在这个函数中，第一个参数是日期/日期时间。该函数返回给定日期值的季度(从 1 到 4 的数字)。1-3 月的日期将返回 1，4-6 月的日期将返回 2，7-9 月的日期将返回 3，10-12 月的日期将返回 4。

**语法:**

```sql
QUARTER( date_value )
```

**功能范围值:**

```sql
1 year = 12/3 = 4 Quarter 
Jan to Mar
Apr to Jun
Jul to Sep
Oct to Nov 
```

**参数:**

<figure class="table">

| parameter | Describe |
| --- | --- |
| date _ value | from which to extract the date or date time value of the quarter. |

</figure>

**返回:**

它将返回日期值的季度部分。

**示例-1 :**

```sql
SELECT QUARTER('2020-02-17');
```

**输出:**

```sql
1
```

**示例-2 :**

```sql
SELECT QUARTER('2020-05-17 15:21:05');
```

**输出:**

```sql
2
```

**示例-3 :**

Curdate()函数将返回系统日期的当前季度

```sql
SELECT QUARTER(CURDATE());
```

**输出:**

```sql
4
```

**2。秒至时间功能:**

在马里亚数据库中，秒到时间函数用于将数字秒转换为时间值。在这个函数中，第一个参数是第二个。此函数返回的时间值范围从“-838:59:59”到“838:59:59”。该函数将结果格式化为“时:分:秒”。它的工作原理与时间到秒函数相反。

**语法:**

```sql
SEC_TO_TIME( seconds )
```

**函数返回值:**

```sql
Range : '-838:59:59' to '838:59:59'
```

**参数:**

<figure class="table">

| **parameter** | **Describe** |
| --- | --- |
| seconds | A number representing seconds. The value can be positive or negative. |

</figure>

**返回:**

返回时间值。

**示例-1 :**

```sql
SELECT SEC_TO_TIME(5);
```

**输出:**

```sql
'00:00:05'
```

**示例-2 :**

```sql
SELECT SEC_TO_TIME(18700);
```

**输出:**

```sql
'05:11:40'
```

**示例-3 :**

```sql
SELECT SEC_TO_TIME(-999);
```

**输出:**

```sql
'-00:16:39'
```