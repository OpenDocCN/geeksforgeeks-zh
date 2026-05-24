# SQL Server 中的数字和日期时间数据类型

> 原文：[https://www.geeksforgeeks.org/numeric-and-date-time-data-type-in-SQL-server/](https://www.geeksforgeeks.org/numeric-and-date-time-data-types-in-sql-server/)

微软 SQL Server 支持多种数据类型。本文中包含了一些更重要的数据类型。在本文中，我们将介绍数值型 SQL server 数据类型和不同的日期时间数据类型。我们一个一个来讨论。

## 数值数据类型

### bit
`bit` 是计算机系统中最小的单位。一个 `bit` 可以是 0 或 1。`bit` 数据类型也可以接受 `NULL` 值。

**语法：**
```sql
column_name bit;
```

一个 `bit` 最多可以占用 8 个字节的存储空间，而 2 个 `bit` 最多可以占用 16 个位，并且循环继续。

### int
一种可以存储整数值（正数和负数）的数据类型。存储大小最多为 8 字节（-2⁶³ 到 2⁶³-1）。它细分为 `tinyint`、`int`、`smallint`、`bigint`。可以根据可存储的字节数来使用它们。

#### (i). bigint
一种数值整数数据类型，最大存储为 8 字节（-2⁶³ 到 2⁶³-1）。它可以存储正值和负值。可用于存储巨大的数字。

**语法：**
```sql
column_name bigint;
```

#### (ii). int
一种数值整数数据类型，存储大小为 4 字节。

**语法：**
```sql
column_name int;
```

#### (iii). smallint
一种存储 2 字节数据的数值整数类型。

**语法：**
```sql
column_name smallint;
```

#### (iv). tinyint
存储 1 个字节的数字数据类型。

**语法：**
```sql
column_name tinyint;
```

例如，班级表中的学生人数可以分配如下。
```sql
rollnumber int;
```

SQL 服务器数值数据类型表：

| 数字数据类型 | 整数大小(字节) |
| --- | --- |
| `bit` | 值(0、1 或空) |
| `tinyint` | 1 |
| `smallint` | 2 |
| `int` | 4 |
| `bigint` | 8 |
| `decimal` | 5 至 17 |
| `numeric(p,s)` | 5 至 17 |
| `smallmoney` | 4 |
| `money` | 8 |
| `float` | 4 或 8 |
| `real` | 4 |

### decimal
一种可以存储十进制值的数据类型。此数据类型可用于存储百分比值。

**语法：**
```sql
column_name decimal(precision, scale)
```

例如：
```sql
percentage decimal(4,3)
```

精度是用于描述从左到右存储的位数的术语，而刻度是用于存储小数点后位数的术语。

## 日期时间数据类型

以电子商务为例，产品交付日期和时间将存储在数据库中。对于这种情况，MS SQL SERVER 支持的数据类型很少：

### date
它以 `yyyy-mm-dd` 的格式存储日期。

**语法：**
```sql
date
```

### time
它基于 24 小时制存储时间。

**语法：**
```sql
time
```

### datetime2
它以 `yyyy-mm-dd hh:mm:ss` 的格式存储日期和时间。

**语法：**
```sql
datetime2
```

有一些数据类型可以存储金钱、唯一标识符、XML 数据等等。但是，在 SQL Server 的未来版本中，由于某种原因，某些数据类型将被删除。确保使用 SQL Server 中可用的数据类型。SQL server 中不同类型的日期时间数据类型表，如下所示：

| 数据类型 | 大小(字节) |
| --- | --- |
| `datetime` | 8 |
| `datetime2` | 6 至 8 |
| `smalldatetime` | 4 |
| `date` | 3 |
| `time` | 3 至 5 |
| `datetimeoffset` | 8 至 10 |
| `timestamp` | 唯一的号码 |