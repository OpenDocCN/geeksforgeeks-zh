# PHP IntlCalendar::equals() 函数

> Original: [https://www.geeksforgeeks.org/php-intlcalendar-equals-function/](https://www.geeksforgeeks.org/php-intlcalendar-equals-function/)

函数 `IntlCalendar::equals()` 是 PHP 中的一个内置函数，用于比较两个 `IntlCalendar` 时间对象，如果该日历和给定日历具有相同的日期，则返回 `TRUE`，否则返回 `FALSE`。

## 语法

*   Object-oriented style:

```php
bool IntlCalendar::equals( IntlCalendar $other )
```

*   Process style:

```php
bool intlcal_equals( IntlCalendar $cal, IntlCalendar $other )
```

## 参数

*   `$cal`: 此参数保存 `IntlCalendar` 资源。
*   `$other`: 此参数保存要与第一个时间对象进行比较的日历日期和时间。

## 返回值

如果两个 `IntlCalendar` 对象的当前时间相同，则此函数返回 `TRUE`，否则返回 `FALSE`。

## 程序示例

下面的程序演示了 PHP 中的 `IntlCalendar::equals()` 函数：

```php
<?php

// Create an IntlCalendar from a DateTime object or string
$calendar1 = IntlCalendar::fromDateTime('2019-03-21 09:19:29');
$calendar2 = IntlCalendar::fromDateTime('2018-03-21 09:19:29');

// Use IntlCalendar::equals() function to compare time
// of two IntlCalendar objects and display result
var_dump($calendar1->equals($calendar2));

// Clone the DateTime of $calendar1
$calendar2 = clone $calendar1;

// Use IntlCalendar::equals() function to compare time
// of two IntlCalendar objects and display result
var_dump($calendar1->equals($calendar2));

// Create an instance of IntlCalendar
$calendar2 = IntlCalendar::createInstance(NULL, 'en_US');

// Set DateTime of $calendar2 to $calendar1
$calendar2->setTime($calendar1->getTime());

// Use IntlCalendar::equals() function to compare time
// of two IntlCalendar objects and display result
var_dump($calendar1->equals($calendar2));

// Clone the DateTime of $calendar1
$calendar2 = clone $calendar1;

// Set DateTime of $calendar2 to $calendar1
$calendar2->setTime($calendar1->getTime() - 10);

// Use IntlCalendar::equals() function to compare time
// of two IntlCalendar objects and display result
var_dump($calendar1->equals($calendar2));

?>
```

## 输出

```php
bool(false)
bool(true)
bool(true)
bool(false)
```

**引用：** [https://www.php.net/manual/en/intlcalendar.equals.php](https://www.php.net/manual/en/intlcalendar.equals.php)