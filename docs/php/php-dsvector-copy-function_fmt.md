# `Ds\Vector::copy()` 函数

> Original: [https://www.geeksforgeeks.org/php-dsvector-copy-function/](https://www.geeksforgeeks.org/php-dsvector-copy-function/)

## 概述

`Ds\Vector::copy()` 函数是 PHP 中的一个内置函数，用于创建给定向量的副本。

## 语法

```php
public Ds\Vector::copy( void ): Ds\Vector
```

## 参数与返回值

**参数：** 此函数不接受任何参数。

**返回值：** 此函数返回向量的浅表副本。

## 示例

以下程序说明了 PHP 中的 `Ds\Vector::copy()` 函数：

### 程序 1

```php
<?php

// Create a vector array
$arr1 = new \Ds\Vector([1, 2, 3, 5]);

// Use copy() function to copy
// the vector array
$arr2 = $arr1->copy();

echo("Original Array \n");

// Display the original array
print_r($arr1);

echo("Copied Array \n");

// Display the copied array
print_r($arr2);

?>
```

发帖主题：Re：Колибри0.7.8.0

### 程序 2

```php
<?php

// Create a vector array
$arr1 = new \Ds\Vector(["geeks", "for", "geeks"]);

// Use copy() function to copy
// the vector array
$arr2 = $arr1->copy();

echo("Original Array\n");

// Display the original array
print_r($arr1);

echo("Copied Array\n");

// Display the copied array
print_r($arr2);

?>
```

发帖主题：Re：Колибри0.7.8.0

## 参考资料

[http://php.net/manual/en/ds-vector.copy.php](http://php.net/manual/en/ds-vector.copy.php)