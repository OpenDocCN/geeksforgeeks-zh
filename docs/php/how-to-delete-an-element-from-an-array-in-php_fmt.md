# 如何在 PHP 中从数组中删除一个元素？

> 原文: [https://www.geeksforgeeks.org/how-to-delete-an-element-from-an-array-in-php/](https://www.geeksforgeeks.org/how-to-delete-an-element-from-an-array-in-php/)

在 PHP 中，有多种方法可以从数组中删除元素。本文讨论了 PHP 中用于从数组中删除元素的一些最常见的方法。

## 使用的函数

*   [`unset()`](https://www.geeksforgeeks.org/php-unset-function/)：此函数接受一个元素作为参数并将其销毁。它不会改变其他元素的键。
*   [`array_splice()`](https://www.geeksforgeeks.org/php-array_splice-function/)：此函数接受三个参数：数组、偏移量（从哪里开始）和长度（要删除的元素数量）。删除元素后，它会自动重新索引索引数组，但不会重新索引关联数组。
*   [`array_diff()`](https://www.geeksforgeeks.org/php-array_diff-function/)：此函数接受数组和数组值列表作为输入，并从数组中删除给定的值。与`unset()`方法类似，其他元素的键不会被改变。

## 所用步骤

*   声明一个[关联数组](https://www.geeksforgeeks.org/associative-arrays-in-php/)。
*   从数组中删除元素。
*   打印结果。
*   声明一个索引数组。
*   从索引数组中删除一个元素。
*   打印结果。

## 示例 1

本示例使用`unset()`函数删除元素。`unset()`函数将数组作为引用，不返回任何内容。

```php
<?php

// Declaring associated array
$ass_arr = ["a"=>"Geeks", "b"=>"For", "c"=>"Geeks"];

// Deleting element associated with key "b"
unset($ass_arr["b"]);

// Printing array after deleting the element
print_r($ass_arr);

// Declaring indexed array
$ind_arr = ["Geeks","For","Geeks"];

// Deleting element and index 1
unset($ind_arr[1]);

// Printing array after deleting the element
print_r($ind_arr);
?>
```

## 输出

```php
Array
(
    [a] => Geeks
    [c] => Geeks
)
Array
(
    [0] => Geeks
    [2] => Geeks
)
```