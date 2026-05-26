# PHP `Ds\Deque::reduce()` 函数

> Original: [https://www.geeksforgeeks.org/php-dsdeque-reduce-function/](https://www.geeksforgeeks.org/php-dsdeque-reduce-function/)

`Ds\Deque::reduce()` 函数是 PHP 中的一个内置函数，用于使用回调函数将 `Deque` 缩减为单个元素。

## 语法

```php
public Ds\Deque::reduce( $callback, $initial ) : mixed
```

## 参数

此函数接受两个参数，如下所述：

*   `$callback`：它包含要对 `Deque` 元素执行的操作，最终产生一个单一元素。
*   `$initial`：它保存携带的初始值，该值将是所有元素操作的结果。

## 返回值

此函数返回回调函数返回的最终值。

下面的程序说明了 PHP 中的 `Ds\Deque::reduce()` 函数：

## 程序 1

```php
<?php

// Declare a deque
$deck = new \Ds\Deque([10, 20, 30, 40, 50, 60]);

echo("Elements of Deque\n");

// Display the Deque elements
print_r($deck);

// Function to perform operation on deque
$func = function($carry, $element) {
    return $carry + $element;
};

echo("\nDeque after reduced into single element: ");

// use reduce() function
var_dump($deck->reduce($func, 5));

?>
```

## 输出

```php
Elements of Deque
Ds\Deque Object
(
    [0] => 10
    [1] => 20
    [2] => 30
    [3] => 40
    [4] => 50
    [5] => 60
)

Deque after reduced into single element: int(215)
```

## 程序 2

```php
<?php

// Declare a deque
$deck = new \Ds\Deque([10, 20, 30, 40, 50, 60]);

echo("Elements of Deque\n");

// Display the Deque elements
print_r($deck);

// Function to perform operation on deque
$func = function($carry, $element) {
    return $carry * $element + 20;
};

echo("\nDeque after reduced into single element: ");

// use reduce() function
var_dump($deck->reduce($func, 10));

?>
```

## 输出

```php
Elements of Deque
Ds\Deque Object
(
    [0] => 10
    [1] => 20
    [2] => 30
    [3] => 40
    [4] => 50
    [5] => 60
)

Deque after reduced into single element: int(8714461220)
```

**引用：**[http://php.net/manual/en/ds-deque.reduce.php](http://php.net/manual/en/ds-deque.reduce.php)