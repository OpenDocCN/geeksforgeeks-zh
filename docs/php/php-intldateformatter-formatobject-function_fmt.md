# PHP `IntlDateFormatter::formatObject()` 函数

> Original: [https://www.geeksforgeeks.org/php-intldateformatter-formatobject-function/](https://www.geeksforgeeks.org/php-intldateformatter-formatobject-function/)

`IntlDateFormatter::formatObject()` 函数是 PHP 中的一个内置函数，用于格式化 `IntlDateFormatter` 对象。此函数允许格式化 `IntlCalendar` 或 `DateTime` 对象。

## 语法

*   Object-oriented style:

```php
*string* IntlDateFormatter::formatObject( *object* $object, 
                             *mixed* $format = NULL, *string* $locale = NULL )
```

*   Process style:

```php
*string* datefmt_format_object( *object* $object,
                             *mixed* $format = NULL, *string* $locale = NULL )
```

## 参数

此函数接受上述三个参数，如下所述：

*   `object`: 此参数保存 `IntlCalendar` 或 `DateTime` 类型的对象。
*   `format`: 此参数保存日期的格式，用于设置给定格式的日期。您可以使用包含两个值的数组（第一个用于设置日期样式，第二个用于设置时间样式）、常量（如 `IntlDateFormatter::None`、`IntlDateFormatter::Short`、`IntlDateFormatter::Medium`、`IntlDateFormatter::Long`、`IntlDateFormatter::Full`）、整数或字符串格式。`Null` 值用于默认样式。
*   `locale`: 此参数保存使用的区域设置。`Null` 值用于默认区域设置。

## 返回值

此函数成功时返回给定格式的字符串，失败时返回 `False`。

## 示例

下面的程序演示了 PHP 中的 `IntlDateFormatter::formatObject()` 函数：

```php
<?php

// Set the timezone and locale
ini_set('date.timezone', 'Asia/Calcutta');
ini_set('intl.default_locale', 'en_US');

// Create an IntlCalendar from a DateTime object or string 
$calander = IntlCalendar::fromDateTime('2019-10-05 09:19:29');

// Display the date in given format
echo "Default date format => " .
    IntlDateFormatter::formatObject($calander) . "\n";

// Display the date in given format
echo "Date in string format => " .
    IntlDateFormatter::formatObject($calander,
    "dd MM yyyy") . "\n";

// Display the date in given format
echo "Date in long format => " .
    IntlDateFormatter::formatObject($calander,
    IntlDateFormatter::TRADITIONAL) . "\n";

// Display the date in given format
echo "Date in array format => ",
    IntlDateFormatter::formatObject($calander, 
    array(
        IntlDateFormatter::NONE,
        IntlDateFormatter::FULL)
    );

?>
```

**输出：**

```
Default date format => Oct 5, 2019, 9:19:29 AM
Date in string format => 05 10 2019
Date in long format => Saturday, October 5, 2019 at 9:19:29 AM India Standard Time
Date in array format => 9:19:29 AM India Standard Time
```

**引用：**[https://www.php.net/manual/en/intldateformatter.formatobject.php](https://www.php.net/manual/en/intldateformatter.formatobject.php)