# IntlCalendar::isWeekend() 函数

> 原文：[https://www.geeksforgeeks.org/php-intlcalendar-isweekend-function/](https://www.geeksforgeeks.org/php-intlcalendar-isweekend-function/)

`IntlCalendar::isWeekend()` 函数是 PHP 中的一个内置函数，用于检查给定的日期/时间是否在周末。

## 语法

*   面向对象风格

```php
bool IntlCalendar::isWeekend( float $date = NULL )
```

*   过程式风格

```php
bool intlcal_is_weekend( IntlCalendar $cal, float $date = NULL )
```

## 参数

此函数使用两个参数，如下所述：

*   `$cal`：此参数保存 `IntlCalendar` 对象的资源。
*   `$date`：此参数保存一个可选的时间戳，表示自纪元以来的毫秒数（不包括闰秒）。如果此参数的值为空，则使用当前时间。

## 返回值

此函数返回一个布尔值，表示给定时间是否发生在周末。

## 程序

下面的程序演示了 PHP 中的 `IntlCalendar::isWeekend()` 函数：

```php
<?php

// 设置时区
ini_set('date.timezone', 'Asia/Calcutta');

// 创建 IntlCalendar 实例
$calendar = IntlCalendar::createInstance('Asia/Calcutta');

// 检查给定的日期时间是否是周末
var_dump($calendar->isWeekend());

// 将日期时间设置到对象中
$calendar->set(2019, 8, 29);

// 检查给定的日期时间是否是周末
var_dump($calendar->isWeekend());

// 设置日期时间对象
$calendar->isWeekend(strtotime('2019-09-22 12:30:00'));

// 检查给定的日期时间是否是周末
var_dump($calendar->isWeekend());

?>
```

## 输出

```php
bool(false)
bool(true)
bool(true)
```

## 引用

[https://www.php.net/manual/en/intlcalendar.isweekend.php](https://www.php.net/manual/en/intlcalendar.isweekend.php)