# array_count_values()函数在PHP中有什么用？

> 原文：[https://www.geeksforgeeks.org/what-is-the-use-of-array_count_values-function-in-php/](https://www.geeksforgeeks.org/what-is-the-use-of-array_count_values-function-in-php/)

在本文中我们将讨论一下 PHP 中的 [`array_count_values()`](https://www.geeksforgeeks.org/php-array_count_values-function/) 函数。

`array_count_values()` 函数用于计算数组中的所有值。换句话说，我们可以说 `array_count_values()` 函数用于计算数组中所有元素的频率。

## 语法

```php
array array_count_values( $array )
```

## 参数

该函数接受单参数 `$array`。这个参数是我们需要计算其中存在的值的计数的数组。

## 返回值

这个函数返回一个带有键值对的关联数组，其中键是作为参数传递的数组元素，值是这些元素在数组中的出现频率。

## 示例

对数组中的值进行计数的 PHP 程序。

### PHP

```php
<?php

// Array of subjects with 4 elements
$array1 = array("Python", "c/cpp", "php", "java");

// Count values in an array
print_r(array_count_values($array1));

?>
```

### 输出

```php
Array
(
    [Python] => 1
    [c/cpp] => 1
    [php] => 1
    [java] => 1
)
```

### 例 2

### PHP

```php
<?php

// Array of subjects with 8 elements
$array1 = array("Python", "c/cpp", "php",
    "java","R programming", "c/cpp", "php", "java");

// Count values in an array
print_r(array_count_values($array1));

?>
```

### 输出

```php
Array
(
    [Python] => 1
    [c/cpp] => 2
    [php] => 2
    [java] => 2
    [R programming] => 1
)
```