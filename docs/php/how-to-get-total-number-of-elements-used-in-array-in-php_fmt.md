# 如何在 PHP 中获取数组中使用的元素总数？

> 原文: [https://www.geeksforgeeks.org/how-to-get-total-number-of-elements-used-in-array-in-php/](https://www.geeksforgeeks.org/how-to-get-total-number-of-elements-used-in-array-in-php/)

在本文中，我们将讨论如何从数组中获取 PHP 中的元素总数。我们可以通过使用 [`count()`](https://www.geeksforgeeks.org/php-count-function/) 和 [`sizeof()`](https://www.geeksforgeeks.org/php-sizeof-function/) 函数来获取数组中元素的总数。

## 使用 `count()` 函数

`count()` 函数用于获取数组中元素的总数。

### 语法

```php
count(array)
```

### 参数
它接受单个参数，即作为输入数组的数组。

### 返回值
返回数组中元素的个数。

### 程序 1
使用 `count()` 函数对数组中的元素进行计数的 PHP 程序。

```php
<?php

// Create an associative array 
// with 5 subjects
$array1 = array(
      0 => 'php',  
      1 => 'java',  
      2 => 'css/html', 
      3 => 'python',
      4 => 'c/c++'
);

// Get total elements in array
echo count( $array1);

?>
```

### 输出

```php
5
```

## 使用 `sizeof()` 函数

[`sizeof()`](https://www.geeksforgeeks.org/php-sizeof-function/) 函数用于计算数组或任何其他可计数对象中存在的元素数量。

### 语法

```php
sizeof(array)
```

### 参数
它只接受一个参数数组，即输入数组。

### 返回值
返回数组中存在的元素个数。

### 示例

```php
Input: array(10,20,30,50)
Output: 4

Input: array("Hello","geeks")
Output: 2
```

### 程序 2
PHP 程序使用 `sizeof()` 函数对元素个数进行计数。

```php
<?php

// Create an associative array
// with 5 subjects
$array1 = array(
      0 => 'php',  
    1 =>'java',  
      2 => 'css/html', 
      3 => 'python',
      4 => 'c/c++'
);

// Get total elements in array
echo sizeof( $array1);

?>
```

### 输出

```php
5
```