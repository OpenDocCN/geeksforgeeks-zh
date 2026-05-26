# PHP `Ds\Set::slice()` 函数

> 原文：[https://www.geeksforgeeks.org/php-dsset-slice-function/](https://www.geeksforgeeks.org/php-dsset-slice-function/)

`Ds\Set::slice()` 函数是 PHP 中的内置函数，用于返回给定范围的子集。

## 语法

```php
public Ds\Set::slice ( int $index [, int $length ] )
```

## 参数

此函数接受上述两个参数：

*   `$index`：此参数保存子集的起始索引。索引值可以是正数或负数。如果索引值为正，则从集合的该索引处开始；如果索引值为负，则从集合末尾开始。
*   `$length`：此参数保存子集的长度。此参数可以取正值和负值。如果长度为正，则子集大小等于给定长度；如果长度为负，则集合从末尾停止那么多值。

## 返回值

此函数返回给定范围的子集。

## 示例

下面的程序演示了 PHP 中的 `Ds\Set::slice()` 函数：

### 程序 1

```php
<?php

// Create new set 
$set = new \Ds\Set([1, 3, 6, 9, 10, 15, 20]);

// Use slice() function to create 
// sub-set and display it 
print_r($set->slice(2));

print_r($set->slice(1, 2));

print_r($set->slice(2, -2));

?>
```

**输出：**

```php
Ds\Set Object
(
    [0] => 6
    [1] => 9
    [2] => 10
    [3] => 15
    [4] => 20
)
Ds\Set Object
(
    [0] => 3
    [1] => 6
)
Ds\Set Object
(
    [0] => 6
    [1] => 9
    [2] => 10
)
```

### 程序 2

```php
<?php

// Create new set
$set = new \Ds\Set(["Geeks", "GFG", "Abc", "for"]);

// Use slice() function to create 
// sub-set and display it 
print_r($set->slice(3));

print_r($set->slice(2, 0));

print_r($set->slice(0, 3));

?>
```

**输出：**

```php
Ds\Set Object
(
    [0] => for
)
Ds\Set Object
(
)
Ds\Set Object
(
    [0] => Geeks
    [1] => GFG
    [2] => Abc
)
```

## 引用

[https://www.php.net/manual/en/ds-set.slice.php](https://www.php.net/manual/en/ds-set.slice.php)