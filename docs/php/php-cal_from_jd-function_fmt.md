# PHP | cal_from_jd()函数

> 原文:[https://www.geeksforgeeks.org/php-cal_from_jd-function/](https://www.geeksforgeeks.org/php-cal_from_jd-function/)

`cal_from_jd()`函数是 PHP 中的一个内置函数，用于将儒略日计数转换为受支持的日历，如公历、法国历、犹太历等。该函数接受两个参数 `$jd` 和 `$calendar` ，并返回包含指定日历的日历信息的数组。

## 语法:

```php
array cal_from_jd( $jd, $calendar )
```

## 参数:

该函数接受两个参数，如上所述，如下所述:

*   `$jd`: 用于指定儒略日计数作为整数。
*   `$calendar`: 用于指定转换日期的日历。支持的日历有公历、儒略历、法国历和犹太历。

## 返回值:

该函数返回一个包含日历信息的数组，列表如下:

*   日期格式为 "月/日/年"
*   月份
*   年份
*   星期几
*   工作日和月份的缩写及全称

## 程序 1:

```php
<?php

// PHP program to implement cal_from_jd()
// and convert date to the CAL_GREGORIAN

$input = unixtojd(mktime(0, 0, 0, 8, 16, 2016));
print_r(cal_from_jd($input, CAL_GREGORIAN));
?>
```

**输出:**

```php
Array
(
    [date] => 8/16/2016
    [month] => 8
    [day] => 16
    [year] => 2016
    [dow] => 2
    [abbrevdayname] => Tue
    [dayname] => Tuesday
    [abbrevmonth] => Aug
    [monthname] => August
)
```

## 程序二:

```php
<?php

// PHP program to implement cal_from_jd()
// and convert date to the CAL_JEWISH calender
$today = unixtojd(mktime(0, 0, 0, 6, 20, 2007));

print_r(cal_from_jd($today, CAL_JEWISH));
?>
```

**输出:**

```php
Array
(
    [date] => 11/4/5767
    [month] => 11
    [day] => 4
    [year] => 5767
    [dow] => 3
    [abbrevdayname] => Wed
    [dayname] => Wednesday
    [abbrevmonth] => Tammuz
    [monthname] => Tammuz
)
```

## 相关文章:

*   [PHP | julianjd()98o](https://www.geeksforgeeks.org/php-juliantojd-function/)
*   [PHP | jdtojulian()98o](https://www.geeksforgeeks.org/php-jdtojulian-function/)

## 参考:

[http://php.net/manual/en/function.cal-from-jd.php](http://php.net/manual/en/function.cal-from-jd.php)