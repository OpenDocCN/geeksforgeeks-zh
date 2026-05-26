# PHP `date_parse_from_format()` 函数

> Original: [https://www.geeksforgeeks.org/php-date_parse_from_format-function/](https://www.geeksforgeeks.org/php-date_parse_from_format-function/)

`date_parse_from_format()` 是 PHP 中的一个内置函数，用于获取根据指定格式格式化的给定日期的信息。函数的作用是：接受两个参数，并返回包含给定日期详细信息的关联数组。

## 语法

```php
array date_parse_from_format ( $format, $date )
```

## 参数

此函数接受上述两个参数，如下所述：

*   `$format`: 用于指定日期格式所需的参数。格式中使用以下参数字符串。
    1.  **日期:**
        *   `d` 和 `j`: 表示月份中的日期，2位数字，带或不带前导零。
        *   `d` 和 `l` 的字面表示：表示一天。
        *   `S`: 月份日期的英文序数后缀，2个字符。在处理中被忽略。
        *   `z`: 年中的日期（从0开始）
    2.  **月份:**
        *   `F` 和 `M`: 月份的文本表示，如 January 或 September
        *   `m` 和 `n` 的数字：月份，带或不带前导零
    3.  **年份:**
        *   `Y`: 年份的完整数字表示，4位数字
        *   `y`: 年份的两位数字表示（假设在1970-2069年范围内，包括）
    4.  **时间:**
        *   `a` 和 `A`: 午前和午后
        *   `g` 和 `h`: 12小时制，带或不带前导零
        *   `G` 和 `H`: 24小时制，带或不带前导零
        *   `I`: 分钟，带前导零
        *   `s`: 秒，带前导零
        *   `u`: 微秒（最多6位）
    5.  **时区:**
        *   时区标识符，或与UTC的小时差，或与UTC的小时和分钟差（带冒号），或时区缩写
    6.  **完整日期/时间:**
        *   `U`: 自Unix纪元以来（1970年1月1日00:00:00 GMT）
    7.  **空格和分隔符:**
        *   ` `（空格）: 制表符
        *   `#`: 以下分隔符之一：`;`, `:`, `/`, `.`, `-`, `(` 或 `)`
        *   `;`, `:`, `/`, `.`, `-`, `(` 或 `)`: 由 `.` 指定的字符。
        *   `?`: 随机字节
        *   `*`: 随机字节，直到下一个分隔符或数字
        *   `!`: 重置所有字段（年、月、日、时、分、秒、分数和时区信息）为Unix纪元
        *   `|`: 重置所有字段为Unix纪元
        *   `|`: 将分数和时区信息转换为Unix纪元（如果它们尚未被解析）
        *   `+`: 如果存在此格式说明符，字符串中的尾随数据不会导致错误，但会发出警告
*   `$date`: 这是一个强制参数，用于表示一个日期。

## 返回值

此函数返回包含日期详细描述的数组。

下面的程序演示了 PHP 中的 `date_parse_from_format()` 函数。

```php
<?php

// Declare and initialize date variable.
$date = "0.9.2018 5:00+01:00";

// Function is used to return the detail about date.
print_r(date_parse_from_format("j.n.Y H:iP", $date));
?>
```

**Output:**

```php
Array
(
    [year] => 2018
    [month] => 9
    [day] => 0
    [hour] => 5
    [minute] => 0
    [second] => 0
    [fraction] => 
    [warning_count] => 1
    [warnings] => Array
        (
            [19] => The parsed date was invalid
        )

    [error_count] => 0
    [errors] => Array
        (
        )

    [is_localtime] => 1
    [zone_type] => 1
    [zone] => -60
    [is_dst] => 
)
```

**程序 2：**

```php
<?php

// Declare and initialize date variable.
$date = "2015.0.9";

// Function is used to return the detail about date.
print_r(date_parse_from_format("Y.z.n", $date));
?>
```

**输出：**

```php
Array
(
    [year] => 2015
    [month] => 9
    [day] => 1
    [hour] => 
    [minute] => 
    [second] => 
    [fraction] => 
    [warning_count] => 0
    [warnings] => Array
        (
        )

    [error_count] => 0
    [errors] => Array
        (
        )

    [is_localtime] => 
)
```

**相关文章：**

*   [php|DATE_SUN_INFO()函数](https://www.geeksforgeeks.org/php-date_sun_info-function/)
*   [PHP|date_sunset()11-13](https://www.geeksforgeeks.org/php-date_sunset-function/)
*   [php|Date_Parse()函数](https://www.geeksforgeeks.org/php-date_parse-function/)

**引用：**[http://php.net/manual/en/function.date-parse-from-format.php](http://php.net/manual/en/function.date-parse-from-format.php)