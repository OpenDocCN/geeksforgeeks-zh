# PHP 数组 `array_search()` 函数

> 原文: [https://www.geeksforgeeks.org/php-array_search-function/](https://www.geeksforgeeks.org/php-array_search-function/)

在本文中，我们将看到如何使用 PHP 中的 `array_search()` 函数来搜索数组中的特定值及对应的返回键，并将通过示例了解其实现。`array_search()` 是 PHP 中的一个内置函数，用于搜索数组中的特定值，如果找到该值，它将返回其对应的键。如果有多个值，那么将返回第一个匹配值的键。

**语法**:
```php
array_search($value, $array, strict_parameter)
```

**参数**: 该函数取如下三个参数:
*   `$value`: 这是一个必填字段，表示要在索引数组中搜索的值。
*   `$array`: 这是一个必填字段，表示需要被搜索的原始数组。
*   `strict_parameter` (可选): 这是一个可选字段，可以设置为 `TRUE` 或 `FALSE`，表示搜索的严格程度。此参数的默认值为 `false`。
    *   如果为 `true`，函数会检查相同类型的元素，即整数 `10` 会被视为与字符串 `"10"` 不同。
    *   如果为 `false`，则不会保持严格性。

**返回值**: 函数返回传递的对应值的键。如果没有找到，则返回 `FALSE`，如果有多个匹配项，则返回第一个匹配项。

**示例**: 下面的程序说明了 PHP 中的 `array_search()` 函数。

## 示例 1

```php
<?php

// PHP function to illustrate the use of array_search()
function Search($value, $array)
{
    return (array_search($value, $array));
}
$array = array(
    "ram",
    "aakash",
    "saran",
    "mohan",
    "saran"
);
$value = "saran";
print_r(Search($value, $array));
?>
```

**输出**:
```php
2
```

## 示例 2

本示例说明了当 `strict_parameter` 设置为 `FALSE` 时函数的工作情况。请注意，数组和要搜索的元素的数据类型是不同的。

```php
<?php

// PHP function to illustrate the use of array_search()
function Search($value, $array)
{
    return (array_search($value, $array, false));
}
$array = array(
    45, 5, 1, 22, 22, 10, 10);
$value = "10";
print_r(Search($value, $array));
?>
```

**输出**:
```php
5
```

## 示例 3

在这个示例中，我们将利用上面的代码来找出如果我们将 `strict_parameter` 作为 `TRUE` 传递会发生什么。

```php
<?php

// PHP function to illustrate the use of array_search()
function Search($value, $array)
{
    return (array_search($value, $array, true));
}
$array = array(45, 5, 1, 22, 22, 10, 10);
$value = "10";
print_r(Search($value, $array));
?>
```

**输出**:
```php
No Output
```

**参考**: [http://php.net/manual/en/function.array-search.php](http://php.net/manual/en/function.array-search.php)