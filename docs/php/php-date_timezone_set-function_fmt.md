# PHP `date_timezone_set()` 函数

> Original: [https://www.geeksforgeeks.org/php-date_timezone_set-function/](https://www.geeksforgeeks.org/php-date_timezone_set-function/)

`date_timezone_set()` 函数是 PHP 中的一个内置函数，用于设置 `DateTime` 对象的时区。此函数返回 `DateTime` 对象，如果失败则返回 `False`。

## 语法

*   **过程式风格：**
    ```php
    date_timezone_set( $object, $timezone )
    ```

*   **面向对象风格：**
    ```php
    DateTime::setTimezone( $timezone )
    ```

## 参数

此函数接受上述两个参数，如下所述：

*   `$object`：这是一个强制参数，指定由 `date_create()` 函数返回的 `DateTime` 对象。
*   `$timezone`：此参数用于设置表示所需时区的 `DateTimeZone` 对象。

## 返回值

此函数成功时返回 `DateTime` 对象，失败时返回 `False`。

下面的程序演示了 PHP 中的 `date_timezone_set()` 函数：

## 程序 1

```php
<?php

// Create DateTime object
$date = date_create('2018-09-15', timezone_open('Asia/Kolkata'));

// Display the date format
echo date_format($date, 'd-m-Y H:i:sP') . "\n";

// Set the date time zone
date_timezone_set($date, timezone_open('Asia/Singapore'));

// Display the date format
echo date_format($date, 'd-m-Y H:i:sP');
?>
```

**输出：**

```
15-09-2018 00:00:00+05:30
15-09-2018 02:30:00+08:00
```

## 程序 2

```php
<?php

// Create DateTime object
$date = new DateTime('2018-09-15', new DateTimeZone('Asia/Kolkata'));

// Display the date format
echo $date->format('d-m-Y H:i:sP') . "\n";

// Set the date time zone
$date->setTimezone(new DateTimeZone('Asia/Singapore'));

// Display the date format
echo $date->format('d-m-Y H:i:sP');
?>
```

**输出：**

```
15-09-2018 00:00:00+05:30
15-09-2018 02:30:00+08:00
```

## 相关文章

*   [php|time_nanosleep() 函数](https://www.geeksforgeeks.org/php-time_nanosleep-function/)
*   PHP|timezone_name_from_abbr()

**引用：**[http://php.net/manual/en/datetime.settimezone.php](http://php.net/manual/en/datetime.settimezone.php)