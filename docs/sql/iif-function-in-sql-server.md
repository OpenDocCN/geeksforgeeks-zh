# SQL Server 中的 IIF()函数

> 原文:[https://www.geeksforgeeks.org/iif-function-in-sql-server/](https://www.geeksforgeeks.org/iif-function-in-sql-server/)

**SQL Server** **IIF()** 函数有三个参数。 **IIF()** 函数判断或评估第一个参数，如果第一个参数为真，则返回第二个参数；否则，它返回第三个参数。 **IIF()** 函数，用于在查询中添加 if-else 逻辑。>

**语法:**

```sql
IIF(boolean_value, true_value, false_value)

```

**语法中使用的参数:**

*   **布尔 _ value–**
    这是一个需要判断的值。它必须是有效的布尔值，否则该函数将引发错误。
*   **真 _ 值–**
    如果布尔值为真，则得出该值。
*   **false _ value–**
    如果布尔值设置为 false，将得到该值。

**要知道的事实:**IIF()函数类似于 CASE 表达式–

```sql
CASE  
   WHEN boolean_expression  
       THEN true_value
   ELSE
       false_value
END

```

**示例-1 :**
使用 IIF()函数检查 40 <是否为 60:

```sql
SELECT  IIF(40 < 60, 'True', 'False') AS Result ; 
```

**输出:** result

True

假设我们有以下名为“**极客表**”的示例表:

| G_id | G_status |
| --- | --- |
| one | three |
| Two | Two |
| three | four |
| four | Two |
| five | three |
| six | one |
| seven | Two |
| eight | one |
| nine | four |
| Ten | one |
| Eleven | four |
| Twelve | three |
| Thirteen | one |
| Fourteen | three |

**示例-2 :**
使用 IIF()函数与表列。
以下示例使用 IIF()函数中的 IIF()函数:

```sql
SELECT    
   IIF(G_status = 1, ‘Waiting’,  
       IIF(G_status=2, ‘InProgress’,
           IIF(G_status=3, ‘Rejected’,
               IIF(G_status=4, ‘Completed’)
           )
       )
   ) AS Status,

   COUNT(G_id) AS Count
FROM Geektable
GROUP BY G_status ; 
```

**输出:**

| 状态 | 数数 |
| --- | --- |
| 等待 | four |
| 进展中 | three |
| 被拒绝 | four |
| 完成 | three |

**示例-3 :**
将 IIF()函数与聚合函数一起使用。
以下示例将 IIF()函数与 SUM()函数结合使用:

```sql
SELECT    
   SUM(IIF(G_status = 1, 1, 0)) AS ‘Waiting’,  
   SUM(IIF(G_status = 2, 1, 0)) AS ‘InProgress’,  
   SUM(IIF(G_status = 3, 1, 0)) AS ‘Rejected’,  
   SUM(IIF(G_status = 4, 1, 0)) AS ‘Completed’,  
   COUNT(*) AS Total

FROM  Geektable;

```

**输出:**
这里，如果状态匹配，IIF()函数的结果为 1 或 0。SUM()函数得出每个状态的编号。

| 等待 | 进展中 | 被拒绝 | 完成 | 总数 |
| --- | --- | --- | --- | --- |
| four | three | four | three | Fifteen |