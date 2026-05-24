# SQL Server 中的 `DATEFROMPARTS()` 函数

> 原文: [https://www.geeksforgeeks.org/datefromparts-function-in-sql-server/](https://www.geeksforgeeks.org/datefromparts-function-in-sql-server/)

## `DATEFROMPARTS()` 函数
这个函数在 SQL Server 中用来从给定的年、月、日的值中返回一个日期。

## 特征
*   该函数用于从年、月和日的规定值中查找日期。
*   该功能属于日期功能。
*   该函数接受三个参数，即年、月和日。
*   该功能不能包括任何带有规定日期的时间。

## 语法
```sql
DATEFROMPARTS(year, month, day)
```

## 参数
该方法接受如下三个参数:
*   `year`: 是指定的年份，4 位数。
*   `month`: 是指定的月份，从 1 到 12。
*   `day`: 为指定日，即 1 日至 31 日。

## 返回
从给定的年、月、日值中返回一个日期。

### 示例-1
使用 `DATEFROMPARTS()` 函数并获取指定的日期。
```sql
SELECT DATEFROMPARTS(2021, 01, 04);
```
**输出:**
```sql
2021-01-04
```

### 示例-2
使用带有变量的 `DATEFROMPARTS()` 函数并获取指定的日期。
```sql
DECLARE @year Int;
SET @year = 2012;
SELECT DATEFROMPARTS(@year, 09, 13);
```
**输出:**
```sql
2012-09-13
```

### 示例-3
使用带有三个变量的 `DATEFROMPARTS()` 函数并获取指定的日期。
```sql
DECLARE @year Int;
DECLARE @month Int;
DECLARE @day Int;
SET @year = 2016;
SET @month = 08;
SET @day = 29;
SELECT DATEFROMPARTS(@year, @month, @day);
```
**输出:**
```sql
2016-08-29
```

### 示例-4
在下面的示例中使用 `DATEFROMPARTS()` 作为默认值并获取输出。
```sql
CREATE TABLE date_from_parts
(
    id_num        INT IDENTITY, 
    message        VARCHAR(150) NOT NULL, 
    generated_at DATETIME NOT NULL
    DEFAULT DATEFROMPARTS(2001, 4, 7), 
    PRIMARY KEY(id_num)
);
INSERT INTO date_from_parts(message)
VALUES('First Message');

INSERT INTO date_from_parts(message)
VALUES('date_from_parts');
SELECT 
    id_num, 
    message, 
    generated_at
FROM 
    date_from_parts;
```
**输出:**

| id_num | message | generated_at |
| :--- | :--- | :--- |
| 1 | First Message | 2001-04-07 00:00:00.000 |
| 2 | date_from_parts | 2001-04-07 00:00:00.000 |

在这里，首先您需要创建一个表，然后在其中插入值，然后使用 `DATEFROMPARTS()` 函数作为默认值生成所需的输出。

**注意:** 对于运行以上代码使用 SQL Server 编译器，也可以使用在线编译器。

## 应用
该功能用于从年、月、日的指定值中查找日期。