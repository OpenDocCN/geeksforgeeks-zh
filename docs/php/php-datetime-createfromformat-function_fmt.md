# PHP DateTime createFromFormat()函数

> Original: [https://www.geeksforgeeks.org/php-datetime-createfromformat-function/](https://www.geeksforgeeks.org/php-datetime-createfromformat-function/)

`DateTime::createFromFormat()`函数是 PHP 中的一个内置函数，它返回一个表示日期和时间格式的新 `DateTime` 对象。

## 语法

*   Object-oriented style:

```php
DateTime DateTime::createFromFormat( string $format, string $time, DateTimeZone $timezone )
```

*   Process style:

```php
DateTime date_create_from_format( string $format, string $time, DateTimeZone $timezone )
```

## 参数

此函数使用三个参数，如上所述，如下所述：

*   `$format`: 是一个必需参数，用于指定日期格式。格式中使用以下参数字符串。
    1.  **date:**
        *   `d` and `j`: 描述月份中的日期。包含带或不带前导零的两个数字。
        *   `D` and `l`: 一天的字面表示。
        *   `S`: 月份日期的英文序数后缀，2个字符。在处理中被忽略。
        *   `z`: 一年中的第几天（从0开始）
    2.  **month:**
        *   `F` and `M`: 月份的文本表示，例如 January 或 September
        *   `m` and `n`: 月份的数字，带或不带前导零
    3.  **year:**
        *   `Y`: 年份的完整数字表示，4位数字
        *   `y`: 年份的两位数字表示（假设在1970-2069范围内，包括）
    4.  **time:**
        *   `a` and `A`: 上午/下午
        *   `g` and `h`: 12小时制，带或不带前导零
        *   `G` and `H`: 24小时制，带或不带前导零
        *   `I`: 分钟，带前导零
        *   `s`: 秒，带前导零
        *   `u`: 微秒（最多6位）
    5.  **time zone:**
        *   时区标识符，或与UTC的小时差，或与UTC的小时和分钟差，或时区缩写
    6.  **full date / time:**
        *   `U`: 自 Unix 纪元以来的秒数（1970年1月1日 00:00:00 GMT）
    7.  **spaces and delimiters:**
        *   ` ` (空格): 制表符
        *   `#`: 以下分隔符之一：`;`, `:`, `/`, `.`, `-`, `(` 或 `)`
        *   `?`: 随机字节
        *   `*`: 随机字节，直到下一个分隔符或数字
        *   `!`: 重置所有字段（年、月、日、时、分、秒、微秒和时区信息）为 Unix 纪元
        *   `|`: 重置所有字段为 Unix 纪元，但不重置时区信息
        *   `+`: 如果存在此格式说明符，字符串中的尾随数据不会导致错误，但会发出警告
*   `$time`: 此参数保存表示时间的字符串。
*   `$timezone`: 此参数保存表示所需时区的 `DateTimeZone` 对象。

## 返回值

此函数成功时返回新的 `DateTime` 对象，失败时返回 `False`。

下面的程序演示了 PHP 中的 `DateTime::createFromFormat()`函数：

## 示例

### 程序 1

```php
<?php

// Calling the DateTime::createFromFormat() function
// with the format 'j-M-Y' and given DateTime is
$datetime = DateTime::createFromFormat('j-M-Y', '30-September-2019');

// Getting the new formatted datetime
echo $datetime->format('Y-m-d');
?>
```

**输出：**

```
2019-09-30
```

### 程序 2

```php
<?php

// Calling the DateTime::createFromFormat() function
// with the format 'j-M-Y' and given DateTime is
$datetime = DateTime::createFromFormat('j-M-Y', '1-oct-2019');

// Getting the new formatted datetime
echo $datetime->format('d-m-Y H:i:s');
?>
```

**输出：**

```
01-10-2019 11:10:06
```

## 引用

[https://www.php.net/manual/en/datetime.createfromformat.php](https://www.php.net/manual/en/datetime.createfromformat.php)