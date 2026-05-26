# date_date_set() 函数

> Original: [https://www.geeksforgeeks.org/php-date_date_set-function/](https://www.geeksforgeeks.org/php-date_date_set-function/)

`date_date_set()` 函数是 PHP 中的内置函数，用于设置新日期。此函数有四个参数 `$object`、`$year`、`$month` 和 `$day`，成功时返回 `DateTime` 对象，失败时返回 `False`。`date_date_set()` 函数是 `DateTime::setDate()` 函数的别名。

## 语法

```php
date_date_set( $object, $year, $month, $day )
```

## 参数

此函数接受上述四个参数，如下所述：

*   `$object`：这是一个必选参数，指定由 `date_create()` 函数返回的 `DateTime` 对象。
*   `$year`：指定日期的年份的必选参数。
*   `$month`：指定日期的月份的必选参数。
*   `$day`：指定日期的日的必选参数。

## 返回值

此函数成功时返回新的 `DateTime` 对象，失败时返回 `False`。

## 示例

下面的程序演示了 PHP 中的 `date_date_set()` 函数。

### 程序 1：打印日期时间的过程样式

```php
<?php

// Date_create() returns a new DateTime object.
$date = date_create();

// date_date_set() function
date_date_set($date, 2018, 8, 31);

// Print the date in a format
echo date_format($date, "Y/m/d");
?>
```

**输出：**

```php
2018/08/31
```

### 程序 2：打印日期时间的面向对象样式

```php
<?php

// Declare DateTime object.
$date = new DateTime();

// date_date_set() function
$date->setDate(2018, 8, 31);

// Print the date in a format
echo $date->format('Y/m/d');
?>
```

**输出：**

```php
2018/08/31
```

## 相关文章

*   [php|DATE_SUN_INFO()函数](https://www.geeksforgeeks.org/php-date_sun_info-function/)
*   [PHP|date_sunise()11-13](https://www.geeksforgeeks.org/php-date_sunrise-function/)
*   [php|DATE_SUB()函数](https://www.geeksforgeeks.org/php-date_sub-function/)

## 引用

[http://php.net/manual/en/function.date-date-set.php](http://php.net/manual/en/function.date-date-set.php)