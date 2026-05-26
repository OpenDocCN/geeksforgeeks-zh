# IntlCalendar::getActualMaximum() 函数

> Original: [https://www.geeksforgeeks.org/php-intlcalendar-getactualmaximum-function/](https://www.geeksforgeeks.org/php-intlcalendar-getactualmaximum-function/)

`IntlCalendar::getActualMaximum()` 函数是 PHP 中的一个内置函数，用于返回当前时间附近的字段相对最大值。

## 语法

*   Object-oriented style

    ```php
    int IntlCalendar::getActualMaximum( int $field )
    ```

*   Process style

    ```php
    int intlcal_get_actual_maximum( IntlCalendar $cal, int $field )
    ```

## 参数

此函数使用上述两个参数：

*   `$cal`: 此参数保存 `IntlCalendar` 的资源。
*   `$field`: 此参数持有 `IntlCalendar` 日期/时间字段常量之一。此字段包含一个介于 0 和 `IntlCalendar::FIELD_COUNT` 之间的整数值。

## 返回值

此函数返回整数值，该整数值表示与给定字段关联的单位中的最大值（如果成功）或 `false`（如果失败）。

下面的程序演示了 PHP 中的 `IntlCalendar::getActualMaximum()` 函数：

## 程序

```php
<?php

// Set the DateTime object
ini_set('date.timezone', 'Asia/Calcutta');

// Declare an IntlCalendar DateTime object
$calendar = IntlCalendar::fromDateTime('2010-09-22');

// Use getActualMaximum() function to the DateTime object
var_dump($calendar->getActualMaximum(IntlCalendar::FIELD_DAY_OF_MONTH));

// Use getActualMaximum() function to the DateTime object
var_dump($calendar->getActualMaximum(IntlCalendar::FIELD_DAY_OF_WEEK_IN_MONTH));

// Use getActualMaximum() function to the DateTime object
var_dump($calendar->getActualMaximum(IntlCalendar::FIELD_MONTH));

// Use getActualMaximum() function to the DateTime object
var_dump($calendar->getActualMaximum(IntlCalendar::FIELD_WEEK_OF_YEAR));

// Use getActualMaximum() function to the DateTime object
var_dump($calendar->getActualMaximum(IntlCalendar::FIELD_WEEK_OF_MONTH));

?>
```

## 输出

```
int(30)
int(5)
int(11)
int(52)
int(5)
```

## 引用

[https://www.php.net/manual/en/intlcalendar.getactualmaximum.php](https://www.php.net/manual/en/intlcalendar.getactualmaximum.php)