# PHP Ds\Vector reduce() 函数

> Original: [https://www.geeksforgeeks.org/php-dsvector-reduce-function/](https://www.geeksforgeeks.org/php-dsvector-reduce-function/)

## 函数介绍

`Ds\Vector::reduce()` 函数是 PHP 中的一个内置函数，它通过在回调函数中应用操作将向量减少到单个值。

## 语法

```php
mixed public Ds\Vector::reduce( $callback, $initial )
```

## 参数

此函数接受上述两个参数，如下所述：

*   `$callback`: 此参数包含对元素进行操作并存储累加值的函数。回调函数接受两个参数：`$carry` 和 `$element`，其中 `$carry` 是函数返回的值，`$element` 是当前迭代中元素的值。
*   `$initial`: 此参数持有累加值的初始值，可以为空。

## 返回值

此函数返回回调函数返回的最终值。

## 示例程序

以下程序说明了 PHP 中的 `Ds\Vector::reduce()` 函数：

### 程序 1

```php
<?php

// Declare new Vector
$vect = new \Ds\Vector([1, 2, 3, 4, 5]);

echo("Vector Elements\n");

print_r($vect);

// callback function with reduce function
echo("\nElement after performing operation\n");
var_dump($vect->reduce(function($carry, $element) {
    return $carry + $element + 2;
}));

?>
```

发帖主题：Re：Колибри0.7.8.0

### 程序 2

```php
<?php

// Declare new Vector
$vect = new \Ds\Vector([10, 20, 30, 40, 50]);

echo("Original vector elements\n");

print_r($vect);

$func_gfg = function($carry, $element) {
    return $carry * $element;
};

echo("\nVector after reducing to single element\n");

// Use reduce() function
var_dump($vect->reduce($func_gfg, 10));

?>
```

发帖主题：Re：Колибри0.7.8.0

**引用：**[http://php.net/manual/en/ds-vector.reduce.php](http://php.net/manual/en/ds-vector.reduce.php)