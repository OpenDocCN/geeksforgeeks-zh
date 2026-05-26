# PHP `collator_sort_with_sort_keys()` 函数

> 原文：[https://www.geeksforgeeks.org/php-collator_sort_with_sort_keys-function/](https://www.geeksforgeeks.org/php-collator_sort_with_sort_keys-function/)

`collator_sort_with_sort_keys()` 函数是 PHP 中的一个内置函数，用于使用指定的排序器和排序键对数组进行排序。

## 语法

*   **过程式风格 (Procedural style):**

```php
bool collator_sort_with_sort_keys( $coll, $arr )
```

*   **面向对象风格 (Object-oriented style):**

```php
bool Collator::sortWithSortKeys( $arr )
```

## 参数

该函数接受两个参数，如下所述：

*   `$coll`：此参数用作排序器对象。它提供比较函数，并支持正确区分区域的排序。
*   `$arr`：此参数用于存储要排序的字符串。

## 返回值

该函数成功时返回 `true`，失败时返回 `false`。

下面的程序说明了 PHP 中的 `collator_sort_with_sort_keys()` 函数。

## 程序 1

```php
<?php

// Declare an array which need to sort
$arr = array( 'Geeks', 'g4g', 'GeeksforGeeks', 'geek' );
$coll = collator_create( 'gs' );

// Sort the array with key value
collator_sort_with_sort_keys( $coll, $arr );

var_export( $arr );
?>
```

### 输出

```php
array (
  0 => 'g4g',
  1 => 'geek',
  2 => 'Geeks',
  3 => 'GeeksforGeeks',
)
```

## 程序 2

```php
<?php

// Declare an array which need to sort
$arr = array( 'Geeks123', 'GeeksABC', 'GeeksforGeeks', 'Geeks' );

// Create collector
$coll = collator_create( 'en_US' );

// Sort the array with key value
collator_sort_with_sort_keys( $coll, $arr );

var_export( $arr );
?>
```

### 输出

```php
array (
  0 => 'Geeks',
  1 => 'Geeks123',
  2 => 'GeeksABC',
  3 => 'GeeksforGeeks',
)
```

## 参考

[http://php.net/manual/en/collator.sortwithsortkeys.php](http://php.net/manual/en/collator.sortwithsortkeys.php)