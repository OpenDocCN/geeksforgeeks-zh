# PHP | `collator_sort()`函数

> 原文: [https://www.geeksforgeeks.org/php-collator_sort-function/](https://www.geeksforgeeks.org/php-collator_sort-function/)

`collator_sort()`函数是 PHP 中的一个内置函数，用于使用指定的排序器对数组进行排序。该函数成功时返回真，失败时返回假。

## 语法

### Program style
```php
bool collator_sort( $coll, $arr, $sort_flag )
```

### Object-oriented style
```php
bool Collator::sort( $arr, $sort_flag )
```

## 参数
该函数接受三个参数，如下所述：

*   `$coll`: 此参数用作排序器对象。
*   `$arr`: 此参数包含要排序的数组。
*   `$sort_flag`: 一个可选参数，用于定义排序类型，可选以下值之一：
    *   `Sorter::sort_regular`: 普通比较项。这是默认排序。
    *   `Sorter::sort_numeric`: 按数字比较项。
    *   `Sorter::sort_string`: 按字符串比较项。

## 返回值
该函数成功时返回真，失败时返回假。

## 示例
下面的程序说明了 PHP 中的 `collator_sort()` 函数：

### 程序 1
```php
<?php
$coll = collator_create( 'en_US' );

// Declare array and initialize it
$arr  = array( 'geek', 'geeK', 'Geek', 'geeks' );

// Sort array
collator_sort( $coll, $arr );

// Display array content
var_export( $arr );
?>
```

**输出:**
```php
array (
  0 => 'geek',
  1 => 'geeK',
  2 => 'Geek',
  3 => 'geeks',
)
```

### 程序 2
```php
<?php
$coll = collator_create( 'en_US' );

// Declare array and initialize it
$arr  = array( 30, 12, 56, 33, 74, 23, 1 );

// Sort array
collator_sort( $coll, $arr );

// Display array content
var_export( $arr );
?>
```

**输出:**
```php
array (
  0 => 1,
  1 => 12,
  2 => 23,
  3 => 30,
  4 => 33,
  5 => 56,
  6 => 74,
)
```

## 相关文章
*   [PHP | `collator_asort()` function](https://www.geeksforgeeks.org/php-collator_asort-function/)
*   [PHP | `collator_compare()` function](https://www.geeksforgeeks.org/php-collator_compare-function/)

## 参考
[http://php.net/manual/en/collator.sort.php](http://php.net/manual/en/collator.sort.php)