# TO_DAYS() 函数在 MySQL 中

> 原文: [https://www.geeksforgeeks.org/to-days-function-in-mysql/](https://www.geeksforgeeks.org/to-days-function-in-mysql/)

## TO_DAYS()

`TO_DAYS()` 函数在 MySQL 中取给定的日期，返回从 0 年开始对应给定日期的天数。`TO_DAYS()` 函数只能用于公历内的日期。

## 语法

```sql
TO_DAYS(date)
```

## 参数

函数只能接受一个参数，如下图：

*   `date` – 要转换的给定日期。

## 返回

该函数将返回一个数字，表示到给定日期为止的总天数。

## 例 1

使用给定的日期编号运行 `TO_DAYS()` 函数。

```sql
SELECT TO_DAYS(950510);
```

**输出:**

| TO_DAYS(950510) |
| :-------------- |
| 728788          |

## 例 2

使用给定的日期格式('年-月-日')运行 `TO_DAYS()` 函数。

```sql
SELECT TO_DAYS('2020-12-26');
```

**输出:**

| TO_DAYS('2020-12-26') |
| :-------------------- |
| 738150                |

## 例 3

使用给定日期格式('YY-M-D')的 `TO_DAYS()` 函数。

**注意** – 完整提及年份并不重要，如本例所示。

```sql
SELECT TO_DAYS('3-4-21');
```

**输出:**

| TO_DAYS('3-4-21') |
| :---------------- |
| 1206              |

## 例 4

以给定的日期格式('YY-M-D')和时间运行 `TO_DAYS()` 函数。

```sql
SELECT TO_DAYS('0000-00-00');
```

**输出:**

| TO_DAYS('0000-00-00') |
| :-------------------- |
| NULL                  |