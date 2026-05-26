# PHP `Ds\Sequence::reduce()` 函数

> 原文：[https://www.geeksforgeeks.org/php-dssequence-reduce-function/](https://www.geeksforgeeks.org/php-dssequence-reduce-function/)

## 函数介绍

`Ds\Sequence::reduce()` 函数是 PHP 中的一个内置函数，用于使用回调函数将序列缩减为单个值。

## 语法

```php
mixed abstract public Ds\Sequence::reduce ( callable $callback [, mixed $initial ] )
```

## 参数

此函数接受上述两个参数，如下所述：

*   `$callback`：此参数包含对元素进行操作并存储累加值的函数。回调函数包含两个参数：`$carry` 和 `$$element`，其中 `$carry` 是函数返回的值，`$element` 是当前迭代中元素的值。
*   `$initial`：此参数保存累加值的初始值，可以为空。

## 返回值

此函数返回回调函数的最终值。

## 示例程序

### 程序 1

```php
<?php

// 声明新序列
$seq = new \Ds\Vector([1, 2, 3, 4, 5]);

echo("Sequence Elements\n");

print_r($seq);

// 使用 reduce 函数的回调函数
echo("\nElement after performing operation\n");

var_dump($seq->reduce(function($carry, $element) { 
    return $carry + $element + 2; 
}));

?>
```

**输出：**

```php
Sequence Elements
Ds\Vector Object
(
    [0] => 1
    [1] => 2
    [2] => 3
    [3] => 4
    [4] => 5
)

Element after performing operation
int(25)
```

### 程序 2

```php
<?php

// 声明新序列
$seq = new \Ds\Vector([10, 20, 30, 40, 50]);

echo("Original sequence elements\n");

print_r($seq);

$func_gfg = function($carry, $element) { 
    return $carry * $element; 
};

echo("\nSequence after reducing to single element\n");

// 使用 reduce() 函数
var_dump($seq->reduce($func_gfg, 10));

?>
```

**输出：**

```php
Original sequence elements
Ds\Vector Object
(
    [0] => 10
    [1] => 20
    [2] => 30
    [3] => 40
    [4] => 50
)

Sequence after reducing to single element
int(120000000)
```

## 引用

[https://www.php.net/manual/en/ds-sequence.reduce.php](https://www.php.net/manual/en/ds-sequence.reduce.php)