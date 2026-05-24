# SQL Server 中的 `SESSIONPROPERTY()` 函数

> 原文: [https://www.geeksforgeeks.org/sessionproperty-function-in-sql-server/](https://www.geeksforgeeks.org/sessionproperty-function-in-sql-server/)

## `SESSIONPROPERTY()` 函数

SQL Server 中的此函数用于返回参数部分中指定的会话设置。

## 功能

*   此函数用于查找会话状态的设置。
*   此函数是一个高级函数。
*   此函数只接受一个参数，即 `option`。

## 语法

```sql
SESSIONPROPERTY(option)
```

## 参数

该方法只接受一个参数，如下所示。

**`option`** – 用于检索会话设置的指定选项。它可以是下面给出的任何一个值，如下所示。

```sql
ANSI_NULLS,
ANSI_PADDING,
ANSI_WARNINGS,
ARITHABORT,
CONCAT_NULL_YIELDS_NULL,
NUMERIC_ROUNDABOUT, and
QUOTED_IDENTIFIER.
```

## 返回

它返回在参数部分指定的会话设置。

## 示例-1

使用 `SESSIONPROPERTY()` 函数并获取输出。

```sql
SELECT SESSIONPROPERTY('ANSI_PADDING');
```

**输出:**

```sql

```

这里，`1` 表示此会话属性已打开。

## 示例-2

使用 `SESSIONPROPERTY()` 函数并获取输出。

```sql
SET ANSI_WARNINGS OFF;
SELECT SESSIONPROPERTY('ANSI_WARNINGS');
```

**输出:**

```sql

```

这里，返回 `0`，因为我们已经关闭了会话属性。

## 示例-3

使用 `SESSIONPROPERTY()` 函数并使用变量获取输出。

```sql
DECLARE @sp VARCHAR(20);
SET @sp = 'CONCAT_NULL_YIELDS_NULL';
SELECT SESSIONPROPERTY(@sp);
```

**输出:**

```sql
NULL
```

这里，返回空值，因为串联输出被认为是空值。

## 示例-4

使用 `SESSIONPROPERTY()` 函数和“`ARITHABORT`”作为参数来获取输出。

```sql
SELECT SESSIONPROPERTY('ARITHABORT');
```

**输出:**

```sql

```

这里，当关闭此属性时，将返回 `0`。

## 应用

此函数用于查找参数部分中指定的会话设置。