# PHP 中如何获取当前年份？

> 原文:[https://www . geesforgeks . org/如何获取当前年份 php/](https://www.geeksforgeeks.org/how-to-get-current-year-in-php/)

日期是一个用于格式化时间戳的内置函数。计算机在 UNIX 时间戳中存储日期和时间。这个时间是以 1970 年 1 月 1 日以来的秒数来计算的。由于这对于人类来说是不切实际的，PHP 将时间戳转换为人类可读且更容易理解的格式。

## 语法:

```php
date( format, timestamp )
```

## 说明:

*   `date()`函数中的`format`参数指定了返回的日期和时间的格式。
*   `timestamp`是一个可选参数。如果未提供，将使用当前的日期和时间。

为了将当前年份作为四位数，`Y`被用作参数 to `date()`函数，如下图所示:

## 程序:

```php
<?php 
// PHP program to get the
// current year

echo "Current Year is :";

// Store the year to
// the variable
$year = date("Y");

// Display the year
echo $year;

?> 
```

## Output:

```php
Current Year is :2019
```

## `date()`函数中可用的格式选项:

`date()`函数的格式参数是一个可以包含多个字符的字符串，允许以各种格式生成日期，如下所示:

*   `D`- 表示星期几（星期一到星期日）的文本。
*   `m`– 带有前导零的月份（01 或 12）。
*   `M`- 表示月份的文本，缩写为（一月到十二月）。
*   `y`– 使用两位数字表示年份（08 或 14）。
*   `Y`– 使用四位数字表示年份（2008 或 2014）。

PHP 是一种专门为 web 开发设计的服务器端脚本语言。您可以通过以下 [PHP 教程](https://www.geeksforgeeks.org/php-tutorials/)和 [PHP 示例](https://www.geeksforgeeks.org/php-examples/)从头开始学习 PHP。