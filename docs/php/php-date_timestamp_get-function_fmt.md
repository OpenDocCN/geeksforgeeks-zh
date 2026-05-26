# PHP `date_timestamp_get()` 函数

> Original: [https://www.geeksforgeeks.org/php-date_timestamp_get-function/](https://www.geeksforgeeks.org/php-date_timestamp_get-function/)

`date_timestamp_get()` 函数是 PHP 中的一个内置函数，用于获取 Unix 时间戳。此函数返回代表日期的 Unix 时间戳。

## 语法

### 过程式风格

```php
int date_timestamp_get( $object )
```

### 面向对象风格

```php
int DateTime::getTimestamp( void )
int DateTimeImmutable::getTimestamp( void )
int DateTimeInterface::getTimestamp( void )
```

## 参数

此函数接受单个参数 `$object`，这是必需的。它用于指定 `date_create()` 函数返回的 `DateTime` 对象。它仅在过程式风格中使用。面向对象风格不接受任何参数。

## 返回值

此函数返回代表日期的 Unix 时间戳。

## 示例程序

下面的程序演示了 PHP 中的 `date_timestamp_get()` 函数：

### 程序 1

```php
<?php

// Create DateTime object
$date = date_create();

// Display Unix timestamp date
echo date_timestamp_get($date);
?>
```

### 输出

```php

```

### 程序 2

```php
<?php

// Create DateTime object
$date = new DateTime();

// Display Unix timestamp date
echo $date->getTimestamp();
?>
```

### 输出

```php

```

## 相关文章

*   [PHP `date_date_set()` 函数](https://www.geeksforgeeks.org/php-date_date_set-function/)
*   [PHP `date_offset_get()` 函数](https://www.geeksforgeeks.org/php-date_offset_get-function/)
*   [PHP `gmstrftime()` 函数](https://www.geeksforgeeks.org/php-gmstrftime-function/)

## 引用

[http://php.net/manual/en/datetime.gettimestamp.php](http://php.net/manual/en/datetime.gettimestamp.php)