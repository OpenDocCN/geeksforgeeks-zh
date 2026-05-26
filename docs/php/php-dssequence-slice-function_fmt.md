# Ds\Sequence::slice() 函数

> 原文：[https://www.geeksforgeeks.org/php-dssequence-slice-function/](https://www.geeksforgeeks.org/php-dssequence-slice-function/)

`Ds\Sequence::slice()` 函数是 PHP 中的一个内置函数，用于返回给定范围的子序列。

## 语法

```php
abstract public Ds\Sequence::slice ( int $index [, int $length ] )
```

## 参数

此函数接受两个参数：

*   `$index`：此参数保存子序列的起始索引。索引值可以是正数或负数。如果索引值为正，则从序列的该索引处开始；如果索引值为负，则从序列末尾开始。
*   `$length`：此参数保存子序列的长度。此参数可以取正值和负值。如果长度为正，则子序列的大小等于给定长度；如果长度为负，则序列在距离末尾该值处停止。

## 返回值

此函数返回给定范围的子序列。

## 示例

下面的程序说明了 PHP 中的 `Ds\Sequence::slice()` 函数：

### 程序 1

```php
<?php

// Create new sequence
$seq = new \Ds\Vector([1, 3, 6, 9, 10, 15, 20]);

// Use slice() function to create
// sub sequence and display it
print_r($seq->slice(2));

print_r($seq->slice(1, 2));

print_r($seq->slice(2, -2));

?>
```

### 程序 2

```php
<?php

// Create new sequence
$seq = new \Ds\Vector(["Geeks", "GFG", "Abc", "for"]);

// Use slice() function to create
// sub sequence and display it
print_r($seq->slice(3));

print_r($seq->slice(2, 0));

print_r($seq->slice(0, 3));

?>
```

## 引用

[http://php.net/manual/en/ds-sequence.slice.php](http://php.net/manual/en/ds-sequence.slice.php)