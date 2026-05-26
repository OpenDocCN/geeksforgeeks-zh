# PHP | `collator_compare()`函数

> 原文: [https://www.geeksforgeeks.org/php-collator_compare-function/](https://www.geeksforgeeks.org/php-collator_compare-function/)

`collator_compare()`函数是 PHP 中的一个内置函数，用于根据排序规则比较两个 Unicode 字符串。

## 语法

### Program style

```php
int collator_compare( $coll, $str1, $str2 )
```

### Object-oriented style

```php
int Collator::compare( $str1, $str2 )
```

## 参数

该函数接受三个参数，如上所述，如下所述:

*   `$coll`: 此参数用作排序器对象。它提供比较功能，并支持区分区域的正确排序。
*   `$str1`: 要比较的第一个字符串。
*   `$str2`: 要比较的第二个字符串。

## 返回值

如果 `str1` 大于 `str2`，则该函数返回如下比较结果:

*   `1`: 如果 `str1` 大于 `str2`。
*   `0`: 如果 `str1` 等于 `str2`。
*   `-1`: 如果 `str1` 小于 `str2`。
*   `Error`: 返回 `False`。

下面的程序说明了 PHP 中的 `collator_compare()`函数:

## 程序 1

```php
<?php

// Declare variable and initialize it
$str1 = 'Geeks';
$str2 = 'geeks';

$coll = collator_create( 'en_US' );

// Compare both strings
$res = collator_compare( $coll, $str1, $str2 );

if ($res === false)
    echo collator_get_error_message( $coll );
else if( $res > 0 )
    echo $str1 . " is greater than " . $str2 . "\n";
else if( $res < 0 )
    echo $str1 . " is less than " . $str2 . "\n";
else
    echo $str1 . " is equal to " . $str2;
?>
```

### 输出

```
Geeks is greater than geeks
```

## 程序 2

```php
<?php

// Declare the variable and initialize it
$str1 = 'GeeksforGeeks';
$str2 = 'GeeksforGeeks';

$coll = collator_create( 'en_US' );

// Compare both strings
$res  = collator_compare( $coll, $str1, $str2 );

if ($res === false)
    echo collator_get_error_message( $coll );
else if( $res > 0 )
    echo $str1 . " is greater than " . $str2 . "\n";
else if( $res < 0 )
    echo $str1 . " is less than " . $str2 . "\n";
else
    echo $str1 . " is equal to " . $str2;
?>
```

### 输出

```
GeeksforGeeks is equal to GeeksforGeeks
```

## 参考

[http://php.net/manual/en/collator.compare.php](http://php.net/manual/en/collator.compare.php)