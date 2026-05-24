# 在 SQL Server 中对存储过程参数使用单引号

> 原文:[https://www . geesforgeks . org/SQL server 中存储过程参数使用单引号/](https://www.geeksforgeeks.org/use-of-single-quotes-for-stored-procedure-parameters-in-sql-server/)

每当将任何值传递给字符数据类型的变量或列时，字符串值周围都会有单引号(")，否则会导致错误。下面我们将讨论 SQL Server 的这个特性(在 SQL Server 中对存储过程参数使用单引号)。

**例 1:**

```sql
DECLARE @inp VARCHAR(100)
SET @inp = 'GeeksforGeeks'
SELECT @inp AS Result
```

**输出:**

<figure class="table">T5】

| 结果 |
| --- |
| 极客锻造 |

</figure>

**例 2:**

```sql
DECLARE @var VARCHAR(100)
SET @var = 'LearningSQL'
SELECT @var AS Result
```

**输出:**

<figure class="table">

| Results |
| --- |
| Learn SQL |

</figure>

现在让我们运行下面的查询，变量周围没有单引号。

**例 1:**

```sql
DECLARE @inp VARCHAR(100)
SET @inp = GeeksforGeeks
SELECT @inp AS Result
```

**输出**

```sql
Msg 107, Level 6, State 1, Line 2
Invalid column name GeeksforGeeks.
```

**例 2:**

```sql
DECLARE @var VARCHAR(100)
SET @var = LearningSQL
SELECT @var AS Result
```

**输出**

```sql
Msg 207, Level 7, State 1, Line 2
Invalid column name LearningSQL.
```

从上面的例子可以看出，我们必须在变量周围使用单引号。

现在让我们用同样的例子来说明[**存储过程**](https://www.geeksforgeeks.org/what-is-stored-procedures-in-sql/) **。**

1.让我们创建一个名为“极客测试”的存储过程。

> CREATE PROCEDURE geek test(@ Inp VARCHAR(100))
> 
> AS
> 
> SELECT @ Inp AS Result
> 
> GO

现在让我们用带单引号的参数调用存储过程。

**例**T0】

**输出**

<figure class="table">T5】

| 结果 |
| --- |
| 极客锻造 |

</figure>

我们可以看到它将给出与之前相同的输出。

2.让我们创建一个名为“ProcTest”的存储过程。

> 创建过程过程测试(@ Var VARCHAR(100))
> 
> AS
> 
> 选择@Var AS 结果
> 
> GO

**现在让我们用带单引号的参数调用存储过程。**

**例**T0】

**输出**

<figure class="table">

| Results |
| --- |
| Learn SQL |

</figure>

我们可以看到它将给出与之前相同的输出。

现在，让我们验证 SQL 特性，并在没有单引号的情况下运行相同的存储过程。

**例**

```sql
EXEC GeekTest GeeksforGeeks
```

**输出**

<figure class="table">T5】

| 结果 |
| --- |
| 极客锻造 |

</figure>

**例**T0】

**输出**

<figure class="table">

| Results |
| --- |
| Learn SQL |

</figure>

**结论:**

向字符数据类型的存储过程参数传递值时，当字符串值不包含任何空格时，单引号是可选的。

**注意:**如果字符串值中有空格，会抛出无效列名的错误。

**例 1:**

极客的极客高管

**输出**

```sql
Msg 107, Level 8, State 2, Line 1
Invalid column name.
```

**例 2:**

exec 抗议学习 sql

**输出**

```sql
Msg 207, Level 9, State 2, Line 1
Invalid column name.
```