# `Ds\Set::sorted()` 函数

> 原文：[https://www.geeksforgeeks.org/php-dsset-sorted-function/](https://www.geeksforgeeks.org/php-dsset-sorted-function/)

`Ds\Set::sorted()` 函数是 PHP 中的内置函数，用于返回给定集合的排序副本。

**语法：**

```php
public Ds\Set::sorted([callable $comparator])
```

**参数：** 此函数接受一个比较器函数，在对集合进行排序时将根据该函数对值进行比较。比较器应根据作为参数传递给它的两个值的比较返回下列值：

*   `1`: 如果第一个元素预期小于第二个元素。
*   `-1`: 如果第一个元素预期大于第二个元素。
*   `0`: 如果第一个元素预期等于第二个元素。

**返回值：** 它返回给定集合的排序副本。

下面的程序说明了 PHP 中的 `Ds\Set::sorted()` 函数：

**程序 1：**

```php
<?php
// PHP program to illustrate sorted() function

$set = new \Ds\Set([20, 10, 30]);

// sort the Set
print_r($set->sorted());

?>
```

**输出：**

```php
Ds\Set Object
(
    [0] => 10
    [1] => 20
    [2] => 30
)
```

**程序 2：**

```php
<?php

// Declare a new set
$set = new \Ds\Set([2, 3, 6, 5, 7, 1, 4]);

$sorted = $set->sorted(function($a, $b) {
    return $b <=> $a;
});

print_r($sorted);

?>
```

**输出：**

```php
Ds\Set Object
(
    [0] => 7
    [1] => 6
    [2] => 5
    [3] => 4
    [4] => 3
    [5] => 2
    [6] => 1
)
```

**引用：** [https://www.php.net/manual/en/ds-set.sorted.php](https://www.php.net/manual/en/ds-set.sorted.php)