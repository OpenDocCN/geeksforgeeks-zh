# IntlCalendar::after() 函数

> 原文：[https://www.geeksforgeeks.org/php-intlcalendar-after-function/](https://www.geeksforgeeks.org/php-intlcalendar-after-function/)

`IntlCalendar::after()` 函数是 PHP 中的一个内置函数，如果对象时间晚于传递对象的时间，则返回 True。

## 语法

*   面向对象风格：

```php
bool IntlCalendar::after( IntlCalendar $other )
```

*   过程式风格：

```php
bool intlcal_after( IntlCalendar $cal, IntlCalendar $other )
```

## 参数

*   `$cal`：此参数保存 `IntlCalendar` 资源。
*   `$other`：此参数保存日历，该日历的时间将与主对象的时间进行比较。

## 返回值

如果对象时间晚于传递对象的时间，则此函数返回 `true`，否则返回 `false`。

## 示例

下面的程序演示了 PHP 中的 `IntlCalendar::after()` 函数：

```php
<?php

// Create an IntlCalendar from a DateTime object or string
$calendar1 = IntlCalendar::fromDateTime('2019-08-29 09:19:29');

// Clone the Calendar date
$calendar2 = clone $calendar1;

// Use IntlCalendar::after() function
// and display result
var_dump($calendar1->after($calendar2));
var_dump($calendar2->after($calendar1));

// Use IntlCalendar::add() function to
// add month in date
$calendar1->add(IntlCalendar::FIELD_MONTH, 1);

// Use IntlCalendar::after() function
// and display result
var_dump($calendar1->after($calendar2));
var_dump($calendar2->after($calendar1));

?>
```

输出：

```
bool(false)
bool(false)
bool(true)
bool(false)
```

**引用：**[https://www.php.net/manual/en/intlcalendar.after.php](https://www.php.net/manual/en/intlcalendar.after.php)