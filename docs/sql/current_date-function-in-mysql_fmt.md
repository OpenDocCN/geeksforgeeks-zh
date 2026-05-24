# MySQL 中的 CURRENT_DATE()函数

> 原文: [https://www.geeksforgeeks.org/current_date-function-in-mysql/](https://www.geeksforgeeks.org/current_date-function-in-mysql/)

在本文中，您将看到如何使用 `current_date` 函数，您将分别看到字符串和数字两种格式。

## CURRENT_DATE :
在这个功能中，你会看到如何使用当前日期功能。在 MySQL 中，日期的格式为 `"YYYY-MM-DD"` (字符串格式) 或 `"YYYYMMDD"` (数字格式)。

## 语法:
```sql
CURRENT_DATE()
```

## 参数:
此功能不接受任何参数。

## 返回–
返回当前日期。

## 示例-1 :
`CURRENT_DATE()`函数查找当前日期。

```sql
SELECT CURRENT_DATE() AS CURR_DATE;
```

**输出:**

| `CURR_DATE` |
| --- |
| 2020-09-22 |

## 示例-2 :
`CURRENT_DATE()`函数以 `YYYYMMDD` 格式查找当前日期。

```sql
SELECT CURRENT_DATE()+0 AS CURR_DATE;
```

**输出:**

| `CURR_DATE` |
| --- |
| 20200922 |

## 示例-3 :
在 `CURRENT_DATE()`函数中添加 3 天，查找下一个日期。

```sql
SELECT CURRENT_DATE()+3 AS NEXT_DATE;
```

**输出:**

| `NEXT_DATE` |
| --- |
| 20200925 |