# MySQL 中的 TIMESTAMPDIFF() 函数

> 原文: [https://www.geeksforgeeks.org/timestampdiff-function-in-mysql/](https://www.geeksforgeeks.org/timestampdiff-function-in-mysql/)

`TIMESTAMPDIFF()` 函数用于在 MySQL 中计算从一个 `DateTime` 表达式减去另一个 `DateTime` 表达式后返回的值。

## 语法

```sql
TIMESTAMPDIFF(unit, expr1, expr2)
```

## 参数

该函数接受三个参数。

### `unit`
表示结果的单位。它可以是下列值之一：
`MICROSECOND`, `SECOND`, `MINUTE`, `HOUR`, `DAY`, `WEEK`, `MONTH`, `QUARTER`, `YEAR`

### `expr1`
第一个日期或日期时间表达式。

### `expr2`
第二个日期或日期时间表达式。

## 返回值
返回减法运算后的日期时间表达式值。

## 示例 1
获取两个指定时间值之间的差值，时间格式为 `YYYY-MM-DD HH:MM:SS`。此处 `expr2` 大于 `expr1`，因此返回值为正。

```sql
SELECT TIMESTAMPDIFF(SECOND, '2010-01-01 10:10:20', '2010-01-01 10:45:59') AS SECONDDIFFERENCE;
```

**输出：**

| Second difference |
| --- |
| 2139 |

## 示例 2
获取两个指定时间值之间的差值，时间格式为 `YYYY-MM-DD HH:MM:SS`。此处 `expr2` 小于 `expr1`，因此返回值为负。

```sql
SELECT TIMESTAMPDIFF(SECOND, '2010-01-01 10:10:20', '2010-01-01 09:45:59') AS SECONDDIFFERENCE;
```

**输出：**

| Second difference |
| --- |
| -1461 |

## 示例 3
当日期以 `YYYY-MM-DD` 格式指定时，计算两个日期值之间的月份差。

```sql
SELECT TIMESTAMPDIFF(MONTH, '2019-08-01', '2020-11-01') AS MONTHDIFFERENCE;
```

**输出：**

| MONTHDIFFERENCE |
| --- |
| 15 |

## 示例 4
使用 `TIMESTAMPDIFF` 函数计算员工的总工作经验。

### 创建员工表
```sql
CREATE TABLE Employee(
    id INT AUTO_INCREMENT PRIMARY KEY,
    Full_Name VARCHAR(50) NOT NULL,
    Joining_Date DATE NOT NULL
);
```

### 插入数据
```sql
INSERT INTO Employee(Full_Name, Joining_Date)
VALUES('Riya Jana', '2000-01-01'),
      ('Sayan Ghosh', '2005-09-26'),
      ('Rinki Sharma', '2014-08-12'),
      ('Aniket Singh', '2019-11-05');
```

现在，使用 `TIMESTAMPDIFF` 计算每位员工以年为单位的工作经验。

```sql
SELECT 
    id,
    Full_Name,
    Joining_Date,
    TIMESTAMPDIFF(YEAR, Joining_Date, '2020-11-26') AS WorkExperience
FROM
    Employee;
```

**输出：**

| id | Full_Name | Joining_Date | WorkExperience |
| --- | --- | --- | --- |
| 1 | Riya Jana | 2000-01-01 | 20 |
| 2 | Sayan Ghosh | 2005-09-26 | 15 |
| 3 | Rinki Sharma | 2014-08-12 | 6 |
| 4 | Aniket Singh | 2019-11-05 | 1 |