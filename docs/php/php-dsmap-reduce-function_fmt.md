# PHP `Ds\Map::reduce()` 函数

> Original: [https://www.geeksforgeeks.org/php-dsmap-reduce-function/](https://www.geeksforgeeks.org/php-dsmap-reduce-function/)

`Ds\Map::reduce()` 函数是 PHP 中的一个内置函数，用于通过使用回调函数应用操作将映射减少到单个值。

## 语法

```php
public Ds\Map::reduce( $callback, $initial ): mixed
```

## 参数

此函数接受上述两个参数，如下所述：

*   `$callback`: 此参数包含对元素进行操作并存储进位的函数。此回调函数包含以下三个参数：
    *   `carry`: 它保存前一个回调的返回值，如果是第一次迭代则为初始值。
    *   `key`: 保存当前迭代的键。
    *   `value`: 保存当前迭代的值。
*   `$initial`: 此参数保存 `carry` 的初始值，可以为空。

## 返回值

此函数返回回调函数返回的最终值。

## 示例

以下程序说明了 PHP 中的 `Ds\Map::reduce()` 函数：

### 程序 1

```php
<?php

// Declare a new map
$map = new \Ds\Map(["a" => 1, "b" => 3, "c" => 5]);

echo("Map Elements\n");

print_r($map);

// Callback function with reduce function
echo("\nElement after performing operation\n");

var_dump($map->reduce(function($carry, $key, $element) {
    return $carry + $element + 2;
}));

?>
```

**输出：**

```php
Map Elements
Ds\Map Object
(
    [0] => Ds\Pair Object
        (
            [key] => a
            [value] => 1
        )

    [1] => Ds\Pair Object
        (
            [key] => b
            [value] => 3
        )

    [2] => Ds\Pair Object
        (
            [key] => c
            [value] => 5
        )

)

Element after performing operation
int(15)
```

### 程序 2

```php
<?php

// Declare new Map elements
$map = new \Ds\Map(["a" => 10, "b" => 20,
            "c" => 30, "d" => 40, "e" => 50]);

echo("Original map elements\n");

print_r($map);

$func_gfg = function($carry, $key, $element) {
    return $carry * $element;
};

echo("\nMap after reducing to single element\n");

// Use reduce() function
var_dump($map->reduce($func_gfg, 10));

?>
```

**输出：**

```php
Original map elements
Ds\Map Object
(
    [0] => Ds\Pair Object
        (
            [key] => a
            [value] => 10
        )

    [1] => Ds\Pair Object
        (
            [key] => b
            [value] => 20
        )

    [2] => Ds\Pair Object
        (
            [key] => c
            [value] => 30
        )

    [3] => Ds\Pair Object
        (
            [key] => d
            [value] => 40
        )

    [4] => Ds\Pair Object
        (
            [key] => e
            [value] => 50
        )

)

Map after reducing to single element
int(120000000)
```

## 引用

[https://www.php.net/manual/en/ds-map.reduce.php](https://www.php.net/manual/en/ds-map.reduce.php)