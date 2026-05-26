# PHP IntlCalendar::createInstance() 函数

> Original: [`https://www.geeksforgeeks.org/php-intlcalendar-createinstance-function/`](https://www.geeksforgeeks.org/php-intlcalendar-createinstance-function/)

`IntlCalendar::createInstance()` 函数是 PHP 中的内置函数，用于创建 `IntlCalendar` 的实例。

## 语法

*   Object-oriented style:
```php
IntlCalendar IntlCalendar::createInstance( mixed $timeZone = NULL, string $locale = "" )
```

*   Process style:
```php
IntlCalendar intlcal_create_instance( mixed $timeZone = NULL, string $locale = "" )
```

## 参数

*   `$timezone`: 此参数保存所使用的时区。
    *   `null`: 这是默认时区。
    *   `IntlTimeZone`: 直接使用。
    *   `DateTimeZone`: 允许以 `DateTimeZone` 格式设置时区。提取 `DateTimeZone` 的标识符并创建一个 ICU 时区对象。
    *   `string`: 一个有效的 ICU 时区标识符。
*   `$locale`: 此参数保存要使用的区域设置，或保存 `NULL` 以使用默认区域设置。

## 返回值

此函数成功时创建 `IntlCalendar` 实例，失败时创建 `NULL`。

下面的程序演示了 PHP 中的 `IntlCalendar::createInstance()` 函数：

### 程序 1

```php
<?php

// Create an IntlCalendar instance
$calendar1 = IntlCalendar::createInstance();

// Create an IntlCalendar from a DateTime object or string
$calendar2 = IntlCalendar::fromDateTime('2019-03-21 09:19:29');

// Use IntlCalendar::before() function
var_dump($calendar1->before($calendar2));
var_dump($calendar2->before($calendar1));

// Use IntlCalendar::before() function
var_dump($calendar1->after($calendar2));
var_dump($calendar2->after($calendar1));

?>
```

**输出：**

```php
bool(false)
bool(true)
bool(true)
bool(false)
```

### 程序 2

```php
<?php

// Create an IntlCalendar from a DateTime object or string
$calendar1 = IntlCalendar::fromDateTime('2019-03-21 09:19:29');

// Create an instance of IntlCalendar
$calendar2 = IntlCalendar::createInstance(NULL, 'en_US');

// Set DateTime of $calendar2 to $calendar1
$calendar2->setTime($calendar1->getTime());

// Use IntlCalendar::equals() function to cCompare time
// of two IntlCalendar objects and display result
var_dump($calendar1->equals($calendar2));

?>
```

**输出：**

```php
bool(true)
```

## 参考

[`https://www.php.net/manual/en/intlcalendar.createinstance.php`](https://www.php.net/manual/en/intlcalendar.createinstance.php)