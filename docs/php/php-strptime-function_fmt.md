# PHP `strptime()` 函数

> Original: [https://www.geeksforgeeks.org/php-strptime-function/](https://www.geeksforgeeks.org/php-strptime-function/)

`strptime()` 函数是 PHP 中的内置函数，用于解析由 `strftime()` 函数生成的时间/日期。日期和格式作为参数发送给 `strptime()` 函数，成功时返回数组，失败时返回 `False`。`strptime()` 函数返回的数组包含以下参数：

*   `tm_sec`: 表示一分钟后的秒数 (0-61)。
*   `tm_min`: 表示分钟 (0-59)。
*   `tm_hour`: 表示从午夜开始的小时数 (0-23)。
*   `tm_mday`: 表示月份中的日期 (1-31)。
*   `tm_mon`: 表示从一月开始的月份 (0-11)。
*   `tm_year`: 表示自 1900 年以来的年份。
*   `tm_wday`: 表示从星期日开始的星期几 (0-6)。
*   `tm_yday`: 表示从 1 月 1 日开始的天数 (0-365)。
*   `unparsed`: 表示未被识别的日期部分。

## 语法

```php
array strptime( $date, $format )
```

## 参数

此函数接受两个参数：

*   `$date`: 必填参数，指定要解析的字符串。
*   `$format`: 必填参数，指定日期中使用的格式。

## 返回值

此函数成功时返回数组，失败时返回 `False`。

## 示例

下面的程序演示了 PHP 中的 `strptime()` 函数：

### 程序 1

```php
<?php

// Declaring the format of date/time
$format = "%d/%m/%Y %H:%M:%S";

// Parsing the date/time
$dt = strftime( $format );
echo "$dt";
print_r(strptime( $dt, $format ));
?>
```

**输出：**

```php
22/08/2018 11:46:57Array
(
    [tm_sec] => 57
    [tm_min] => 46
    [tm_hour] => 11
    [tm_mday] => 22
    [tm_mon] => 7
    [tm_year] => 118
    [tm_wday] => 3
    [tm_yday] => 233
    [unparsed] => 
)
```

### 程序 2

```php
<?php

// Declaring a different format of date/time
$format="%d/%m/%y %I:%M:%S";

// Parsing the date/time
$dt = strftime( $format );
echo "$dt";
print_r(strptime( $dt, $format ));
?>
```

**输出：**

```php
22/08/18 11:46:59Array
(
    [tm_sec] => 59
    [tm_min] => 46
    [tm_hour] => 11
    [tm_mday] => 22
    [tm_mon] => 7
    [tm_year] => 118
    [tm_wday] => 3
    [tm_yday] => 233
    [unparsed] => 
)
```

## 相关文章

*   [PHP `gmdate()` 函数](https://www.geeksforgeeks.org/php-gmdate-function/)
*   [PHP `date_parse()` 函数](https://www.geeksforgeeks.org/php-date_parse-function/)

## 引用

[http://php.net/manual/en/function.strptime.php](http://php.net/manual/en/function.strptime.php)