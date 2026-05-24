# SQL Server 中的确定性和不确定性函数

> 原文: [https://www.geeksforgeeks.org/deterministic-and-nondeterministic-functions-in-sql-server/](https://www.geeksforgeeks.org/deterministic-and-nondeterministic-functions-in-sql-server/)

## 1. 确定性函数
每次用一组固定的输入值调用确定性函数并给定相同的数据库条件时，确定性函数总是产生相同的输出。例如，给定上述条件，`AVG()`函数总是得到相同的结果。

## 2. 不确定性函数
不确定性函数每次用一组固定的输入值调用时都会导致不同的输出，即使它们访问的数据库状态保持不变。例如，`GETDATE()`函数，结果当前日期和时间值，总是不同的值。

## 内置函数决定论
你不能影响任何内置函数的决定论。根据由 SQL Server 实现的函数的属性，内置函数可能是确定性的，也可能是不确定性的。例如，在任何查询中使用 `ORDER BY` 子句都不会改变查询中使用的函数的确定性。

### 确定性内置函数有

| 函数 | 函数 |
| --- | --- |
| `ABS` | `DATEDIFF` |
| `ACOS` | `DAY` |
| `ASIN` | `DEGREES` |
| `ATAN` | `EXP` |
| `CEILING` | `FLOOR` |
| `COALESCE` | `ISNULL` |
| `COS` | `ISNUMERIC` |
| `COT` | `LOG` |
| `DATALENGTH` | `LOG10` |
| `DATEADD` | `MONTH` |
| `DATEPART` | `NULLIF` |
| `POWER` | `SQUARE` |
| `RADIANS` | `SQRT` |
| `RAND` | `STR` |
| `ROUND` | `SIN` |
| `SIGN` | `TAN` |
| `YEAR` | `UNICODE` |

以下函数并不总是确定的，但当以确定的方式指定时，它们可能是确定的：

*   在与 `DateTime`、`smalldatetime` 或 `sql_variant` 一起使用之前，`CAST` 是确定性的。
*   只有在与 `CONVERT` 函数一起使用时，`ISDATE` 才是确定性的。
*   在这些条件之一存在之前，`CONVERT` 是确定性的。
    1.  源类型可以是 `sql_variant`。
    2.  目标类型可以是 `sql_variant` & 它的源类型是不确定的。

### 不确定的内置函数有

| 函数 | 函数 |
| --- | --- |
| `@@CONNECTIONS` | `LAG` |
| `@@DBTS` | `LAST_VALUE` |
| `@@IDLE` | `LEAD` |
| `@@CPU_BUSY` | `MIN_ACTIVE_ROWVERSION` |
| `@@IO_BUSY` | `NEWID` |
| `@@PACK_RECEIVED` | `NEWSEQUENTIALID` |
| `@@MAX_CONNECTIONS` | `NEXT VALUE FOR` |
| `@@PACK_SENT` | `NTILE` |
| `@@PACKET_ERRORS` | `PARSENAME` |
| `@@TIMETICKS` | `PERCENTILE_CONT` |
| `@@TOTAL_ERRORS` | `PERCENTILE_DISC` |
| `@@TOTAL_READ` | `CUME_DIST` |
| `@@TOTAL_WRITE` | `PERCENT_RANK` |
| `GETUTCDATE` | `FORMAT` |
| `GETDATE` | `EDGE` |
| `GET_TRANSMISSION_STATUS` | `DENSE_RANK` |
| `CURRENT_TIMESTAMP` | `FIRST_VALUE` |
| `RANK` | `ROW_NUMBER` |