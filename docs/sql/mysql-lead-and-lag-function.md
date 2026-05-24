# MySQL | LEAD()和 LAG()函数

> 原文:[https://www.geeksforgeeks.org/mysql-lead-and-lag-function/](https://www.geeksforgeeks.org/mysql-lead-and-lag-function/)

MySQL 中的 LEAD()和 LAG()函数用于获取分区中任何一行的前后值。这些函数被称为非聚集窗口函数。

**窗口**功能是对分区或窗口的每一行执行操作的功能。这些函数为每个查询行生成的结果不太可能是将它们分组并在一行中生成结果的聚合函数。

*   发生操作的行称为当前行。
*   与当前行相关的行集或使用哪个函数对当前行进行操作的行集称为窗口。

LAG()函数用于从当前行之前的行获取值。

LEAD()函数用于从当前行后面的行中获取值。

**语法:**
用于 LEAD()函数-

```sql
LEAD(expr, N, default) 
          OVER (Window_specification | Window_name)
```

对于 LAG()函数-

```sql
LAG(expr, N, default) 
          OVER (Window_specification | Window_name)
```

函数中的 **N** 和**默认**参数是可选的。

**使用的参数:**

1.  **表达式:**它可以是一个列或任何内置函数。
2.  **N:** 它是一个正值，决定当前行之前/之后的行数。如果它在查询中被省略，那么它的默认值是 1。
3.  **默认值:**是函数返回的默认值，以防没有行领先/落后于当前行 **N** 行。如果缺少，则默认为空。
4.  **OVER():** 它定义了如何将行划分为组。如果 OVER()为空，则函数使用所有行计算结果。
5.  **Window_specification:** 它由查询分区子句组成，该子句决定了查询行的分区和排序方式。
6.  **窗口名称:**如果在查询的其他地方指定了窗口，则使用该窗口名称引用该窗口。

**例:**
考虑一个“争用”表:-

<figure class="table">

| 【c _ id】 | 【开始 _ 日期】 | 结束日期 |  | 【2015-02-08】 | 【2015-02-10】 |
|  | 【2015-02-10】 |  |

</figure>

在上表中，“c_id”代表竞赛 id，“start_date”和“end_date”分别代表竞赛的开始和结束日期。

**问题描述:**我们必须找到一场比赛在下一场比赛中崩溃的天数，即两场比赛都举行的天数。

**查询:**

```sql
Select c_id, start_date, end_date, 
        end_date - lead (start_date) 
        over (order by start_date) 
               + 1 as 'no_of_days' 
                   from contest;
```

在上面的查询中“end_date”返回当前竞赛的结束日期，lead(start_date)返回下一个竞赛的开始日期。因此，这两个日期之间的差值加上 1 将返回比赛碰撞的天数。

这里，窗口说明由“order by”子句给出，该子句表示 lead()函数将按其“start_date”递增顺序对表顺序进行操作。因为它们没有 partition 子句，所以整个表被当作一个窗口。

**输出:**

<figure class="table">【end _ date】

|  | 【c _ id】 | 【开始 _ 日期】 | 【天数】 | 【2015-02-06】 | 【2015-02-09】 |  |
| --- | --- | --- | --- | --- | --- | --- |
|  | 【2015-02-08】 |
| --- | --- |

</figure>

从那以后，第七场比赛之后就没有比赛了(即 c_id=7)。因此，销售线索(起始日期)返回空值。

**注意:**LEAD()和 LAG()函数总是与 **OVER()** 一起使用。缺少 over 子句将会引发错误。