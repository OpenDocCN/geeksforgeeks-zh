# PHP 中的 `Ds\Sequence::sort()` 函数

> 原文：[https://www.geeksforgeeks.org/php-dssequence-sort-function/](https://www.geeksforgeeks.org/php-dssequence-sort-function/)

`Ds\Sequence::sort()` 函数是 PHP 中的一个内置函数，用于对同一位置的 Sequence 元素进行排序。

## 语法

```php
abstract public Ds\Sequence::sort([ callable $comparator ] ): void
```

## 参数

此函数接受单个参数 `$comparator`，该参数用于保存比较函数。比较函数返回小于、大于或等于零的整数值。

## 返回值

此函数不返回任何值。

## 示例程序

### 程序 1

```php
<?php

// Create new sequence
$seq = new \Ds\Vector([2, 4, 1, 9, 6, 5, 12, 9]);

// Use sort() function to sort
// the sequence element
$seq->sort();

print_r($seq);

?>
```

### 程序 2

```php
<?php

// Create new sequence
$seq = new \Ds\Vector([2, 4, 1, 9, 6, 5, 12, 9]);

// Use sort() function to sort
// the sequence element
$seq->sort(function($x, $y) {
    return $y <=> $x;
});

print_r($seq);

?>
```

## 引用

[http://php.net/manual/en/ds-sequence.sort.php](http://php.net/manual/en/ds-sequence.sort.php)