# MySQL 中的各种字符串、数字和日期时间函数

> 原文：[https://www.geeksforgeeks.org/various-string-numeric-and-date-time-functions-in-mysql/](https://www.geeksforgeeks.org/various-string-numeric-and-date-time-functions-in-mysql/)

函数是一种特殊类型的预定义命令集，它执行一些操作并返回一个值。函数对提供给它们的零个、一个、两个或多个值进行操作。提供给函数的值称为参数或自变量。

MySQL 函数被分为不同的类别，如字符串函数、数学函数、日期和时间函数等。虽然 MySQL 提供了大量的函数，但是在本讨论中，我们将只讨论一些常用函数。

## 1. 字符串函数

MySQL 的字符串函数可以通过多种方式操纵文本字符串。下面讨论一些常用的字符串函数：

| 序号 | 函数 | 描述 | 示例 |
| :--- | :--- | :--- | :--- |
| 1. | `CHAR()` | 返回每次整数传递的字符 | 1. `SELECT CHAR(70,65,67,69);` <br> 2. `SELECT CHAR(65,67.3,69.3);` |
| 2. | `CONCAT()` | 返回串联字符串 | `SELECT CONCAT(name, aggregate) AS ‘NameAggregate’ FROM students WHERE age = 14 OR age = 16;` |
| 3. | `LOWER()` / `LCASE()` | 以小写形式返回参数 | 1. `SELECT LOWER(“GFG”) AS “Lower 1”, LCASE(“GFG”) AS “Lower 2”;` |
| 4. | `SUBSTRING()`, `SUBSTR()` | 返回指定的子字符串 | 1. `SELECT SUBSTR(‘ABSDEFG’, 3, 4) AS “Subs”;` <br> 2. `SELECT SUBSTRING(‘ABCDEFG’, -5, 4) AS “Substring”;` |
| 5. | `UPPER()` / `UCASE()` | 转换为大写 | `SELECT UPPER(‘gfg’) AS “UPPER”;` 或 `SELECT UCASE(‘gfg’) AS “UPPER”;` |
| 6. | `TRIM()` | 删除前导和尾随空格 | `SELECT TRIM(‘  First栏  ‘);` |
| 7. | `LENGTH()` | 以字节为单位返回字符串的长度 | `SELECT LENGTH(“CANDIDE”) AS “Character Length”;` |

## 2. 数字函数

数字函数是接受数值并在执行所需操作后返回数值的函数。下面讨论一些有用的数字函数：

| 序号 | 函数 | 描述 | 示例 |
| :--- | :--- | :--- | :--- |
| 1. | `MOD()` | 通过将一个表达式代入另一个表达式，返回该表达式的余数。 | `SELECT MOD(11, 4) AS “Modulus”;` |
| 2. | `POWER()` / `POW()` | 返回一个表达式的值乘以另一个表达式的幂 | `SELECT POWER(3, 2) AS “Raised”;` |
| 3. | `ROUND()` | 返回舍入到整数的数值表达式。可用于将表达式舍入到小数位数。 | `SELECT ROUND(15.193, 1) AS “Round”;` |
| 4. | `SIGN()` | 这个函数返回给定数字的符号。 | `SELECT SIGN(-15) AS “Sign”;` |
| 5. | `SQRT()` | 返回数值表达式的非负平方根。 | `SELECT SQRT(26) AS “SquareRoot”;` |
| 6. | `TRUNCATE()` | 返回数字 `exp1` 截断到 `exp2` 小数位。如果 `exp2` 为 0，则结果没有小数点 | `SELECT TRUNCATE(15.79, 1) AS “TRUNCATE”;` |

## 3. 日期和时间函数

日期函数对日期数据类型的值进行操作。

| 序号 | 函数 | 描述 | 示例 |
| :--- | :--- | :--- | :--- |
| 1 | `CURDATE()` / `CURRENT_DATE()` / `CURRENT_DATE` | 返回当前日期。 | `SELECT CURDATE();` |
| 2 | `DATE()` | 提取日期或日期时间表达式的日期部分。 | `SELECT DATE(‘2020-12-31 01:02:03’);` |
| 3 | `MONTH()` | 返回过去日期的月份。 | `SELECT MONTH(‘2020-12-31’);` |
| 4 | `YEAR()` | 返回年份 | `SELECT YEAR(‘2020-12-31’);` |
| 5 | `NOW()` | 返回函数执行的时间。 | `SELECT NOW();` |
| 6 | `SYSDATE()` | 返回当前日期和时间。 | `SELECT NOW(), SLEEP(2), NOW();` 或 `SELECT SYSDATE(), SLEEP(2), SYSDATE();` |