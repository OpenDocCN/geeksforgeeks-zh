# PHP `date_time_set()` 函数

> Original: [https://www.geeksforgeeks.org/php-date_time_set-function/](https://www.geeksforgeeks.org/php-date_time_set-function/)

`date_time_set()` 函数是 PHP 中的一个内置函数，用于设置时间。此函数用于将 `DateTime` 对象的当前时间重置为不同的时间。

## 语法

*   **Procedural style:**

```php
date_time_set( $object, $hour, $minute, $second, $microseconds )
```

*   **Object-oriented style:**

```php
DateTime::setTime( $hour, $minute, $second, $microseconds )
```

## 参数

此函数接受上述五个参数，如下所述：

*   `$object`: 这是一个强制参数，指定由 `date_create()` 函数返回的 `DateTime` 对象。
*   `$Hour`: 此参数用于设置小时。
*   `$min`: 此参数用于设置分钟。
*   `$Second`: 此参数用于设置秒数。
*   `$microsec`: 此参数用于设置微秒。

## 返回值

此函数成功时返回 `DateTime` 对象，失败时返回 `False`。

下面的程序演示了 PHP 中的 `date_time_set()` 函数：

### 程序 1

```php
<?php

// Create an DateTime object
$date = date_create('2018-09-15');

// Set the new DateTime
date_time_set($date, 8, 30);

// Display the date in given format
echo date_format($date, 'd-m-Y H:i:s') . "\n";

// Set the new DateTime
date_time_set($date, 12, 40, 30);

// Display the date in given format
echo date_format($date, 'Y-m-d H:i:s') . "\n";
?>
```

**输出：**

```php
15-09-2018 08:30:00
2018-09-15 12:40:30
```

### 程序 2

```php
<?php

// Create DateTime object
$date = new DateTime('2018-09-15');

// Set the new DateTime
$date->setTime(12, 30);

// Display the date in given format
echo $date->format('d-m-Y H:i:s') . "\n";

// Set the new DateTime
$date->setTime(12, 30, 20);

// Display the date in given format
echo $date->format('Y-m-d H:i:s');
?>
```

**输出：**

```php
15-09-2018 12:30:00
2018-09-15 12:30:20
```

## 相关文章

*   [PHP `TIMEZONE_OPEN()` 函数](https://www.geeksforgeeks.org/php-timezone_open-function/)
*   [PHP `TIMEZONE_ABBREVIATIONS_LIST()` 函数](https://www.geeksforgeeks.org/php-timezone_abbreviations_list-function/)
*   [PHP `TIMEZONE_LOCATION_GET()` 函数](https://www.geeksforgeeks.org/php-timezone_location_get-function/)

## 引用

[http://php.net/manual/en/datetime.settime.php](http://php.net/manual/en/datetime.settime.php)