# SQL Server 中的确定性和不确定性函数

> 原文:[https://www . geesforgeks . org/确定性和不确定性 SQL server 中的函数/](https://www.geeksforgeeks.org/deterministic-and-nondeterministic-functions-in-sql-server/)

**1。确定性函数:**
每次用一组固定的输入值调用确定性函数并给定相同的数据库条件时，确定性函数总是产生相同的输出。例如，给定上述条件，AVG()函数总是得到相同的结果。

**2。不确定性函数:**
不确定性函数每次用一组固定的输入值调用时都会导致不同的输出，即使它们访问的数据库状态保持不变。例如，GETDATE()函数，结果当前日期和时间值，总是不同的值。

**内置函数决定论:**
你不能影响任何内置函数的决定论。根据由 SQL Server 实现的函数的属性，内置函数可能是确定性的，也可能是不确定性的。例如，在任何查询中使用 ORDER BY 子句都不会改变查询中使用的函数的确定性。

**确定性内置函数有:**

<center>

| 防抱死制动装置 | DATEDIFF(日期差异) |
| 力量 | 阿科斯 |
| 天 | 弧度 |
| 印度历的 7 月 | 度 |
| 轮次 | 阿坦 |
| 经历 | 符号 |
| ATN2 | 地面 |
| 地面 | 犯罪 |
| 天花板 | 是空的 |
| 平方 | 联合 |
| ISNUMERIC | SQRT(工作站) |
| 日期 | NULLIF |
| 装货付款(Cash On Shipment) | LOG10 |
| 原木 | 年 |
| 黝黑色 | 数据长度 |
| 小屋 | 月 |

</center>

以下函数并不总是确定的，但当以确定的方式指定时，它们可能是确定的:

*   在与 DateTime、smalldatetime 或 sql_variant 一起使用之前，CAST 是确定性的。
*   只有在与 CONVERT 函数一起使用时，ISDATE 才是确定性的。
*   在这些条件之一存在之前，CONVERT 是确定性的。
    1.  源类型可以是 sql_variant。
    2.  目标类型可以是 sql_variant &它的源类型是不确定的。

**不确定的内置函数有:**

<center>

| @@CONNECTIONS | 落后 |
| DBTS(数据库服务器) | 最后值 |
| @@IDLE | 导致 |
| @@CPU_BUSY | min _ active _ 版本 |
| @@IO_BUSY | 改变 |
| @@PACK_RECEIVED | NEWSEQUENTIALID |
| @@MAX_CONNECTIONS | 的下一个值 |
| @@PACK_SENT | NTILE |
| @@PACKET_ERRORS | PARSENAME |
| @@TIMETICKS | 百分制 _CONT |
| @@TOTAL_ERRORS | 百分点 _DISC |
| @@TOTAL_READ | cume _ dist |
| @@TOTAL_WRITE | 百分比 _ 等级 |
| getuTCDATE(获取 tcdate) | 格式 |
| 盖达特 | 边缘 |
| 获取传输状态 | 密集 _ 等级 |
| 当前时间戳 | 第一个值 |
| 等级 | 行号 |

</center>