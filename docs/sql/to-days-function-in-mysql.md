# 至天数()函数在 MySQL 中

> 原文:[https://www.geeksforgeeks.org/to-days-function-in-mysql/](https://www.geeksforgeeks.org/to-days-function-in-mysql/)

**至天数():**

**TO DAYS()函数**在 MySQL 中取给定的日期，返回从 0 年开始对应给定日期的天数。
TO DAYS()函数只能用于公历内的日期。

**语法:**

```sql
TO DAYS(date)
```

**参数:**函数只能接受一个参数，如下图-

*   **日期–**要转换的给定日期。

**返回:**

该函数将返回一个数字，表示到给定日期为止的总天数

**例 1:**

使用给定的日期编号运行结束日期()函数。

```sql
SELECT TO_DAYS(950510);
```

**输出:**

<figure class="table">

| **TO _ DAYS(950510)** |
| 728788 |

</figure>

**例 2:**

使用给定的日期格式('年-月-日')运行截止日期()函数

```sql
SELECT TO_DAYS('2020-12-26');
```

**输出:**

<figure class="table">

| **TO _ DAYS(【2020-12-26】)** |
| 738150 |

</figure>

**例 3:**

使用给定日期格式(' YY-M-D ')的截止日期()函数，

**注意–**完整提及年份并不重要，如本例所示-

```sql
SELECT TO_DAYS('3-4-21');
```

**输出:**

<figure class="table">

| 至 _ 天(' 3-4-21 ') |
| 1206 |

</figure>

**例 4:**

以给定的日期格式(' YY-M-D ')和时间运行截止日期()函数。

```sql
SELECT TO_DAYS('0000-00-00');
```

**输出:**

<figure class="table">

| **TO _ DAYS(【0000-00-00】)** |
| NULL |

</figure>