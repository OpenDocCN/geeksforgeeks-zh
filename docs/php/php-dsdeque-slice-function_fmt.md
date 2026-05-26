# PHP `Ds\Deque::slice()` 函数

> Original: [https://www.geeksforgeeks.org/php-dsdeque-slice-function/](https://www.geeksforgeeks.org/php-dsdeque-slice-function/)

## 函数介绍

`Ds\Deque::slice()` 函数是 PHP 中的一个内置函数，用于返回子 Deque，其中包含索引范围内的 Deque 元素。

## 语法

```php
public Ds\Deque::slice( $index, $length ) : Ds\Deque
```

## 参数

此函数接受上述两个参数，如下所述：

*   `index`: 此参数保存子 Deque 的起始索引。索引值可以是正数或负数。如果索引值为正，则从 Deque 的开头开始计数；如果索引值为负，则从 Deque 的末尾开始计数。
*   `length`: 此参数保存子队列的长度。此参数可以接受正值和负值。如果长度为正，则子队列大小等于给定长度；如果长度为负，则 Deque 从末尾停止相应数量的值。

## 返回值

此函数返回子队列，其中包含给定范围的队列中的切片元素。

## 示例程序

### 程序 1

```php
<?php

// Declare a deque
$deck = new \Ds\Deque([1, 2, 3, 4, 5, 6]);

echo("Elements of Deque\n");

// Display the Deque elements
print_r($deck);

// Slicing deque from 2 to 5
$deck_new = $deck->slice(2, 5);

echo("\nDeque after slicing:\n");

// Display the Deque elements
print_r($deck_new);

?>
```

### 输出

```php
Elements of Deque
Ds\Deque Object
(
    [0] => 1
    [1] => 2
    [2] => 3
    [3] => 4
    [4] => 5
    [5] => 6
)

Deque after slicing:
Ds\Deque Object
(
    [0] => 3
    [1] => 4
    [2] => 5
    [3] => 6
)
```

### 程序 2

```php
<?php

// Declare a deque
$deck = new \Ds\Deque([1, 2, 3, 4, 5, 6]);

echo("Elements of Deque\n");

// Display the Deque elements
print_r($deck);

// Slicing deque from 3 to -2
$deck_new = $deck->slice(3, -2);

echo("\nDeque after slicing:\n");

// Display the Deque elements
print_r($deck_new);

?>
```

### 输出

```php
Elements of Deque
Ds\Deque Object
(
    [0] => 1
    [1] => 2
    [2] => 3
    [3] => 4
    [4] => 5
    [5] => 6
)

Deque after slicing:
Ds\Deque Object
(
    [0] => 4
)
```

## 引用

[http://php.net/manual/en/ds-deque.slice.php](http://php.net/manual/en/ds-deque.slice.php)