# PHP 中数组值如何转换成小写？

> 原文: [https://www.geeksforgeeks.org/how-to-convert-array-values-to-lowercase-in-php/](https://www.geeksforgeeks.org/how-to-convert-array-values-to-lowercase-in-php/)

给定一个包含大写字符串元素的数组，任务是将数组元素（大写）转换为小写。在 PHP 中，有两种方法可以将数组值转换为小写。

*   使用 `foreach` 循环
*   使用 `array_map()` 函数

## 使用 `foreach` 循环

在这种方法中，迭代器逐个遍历数组的值，并将每个数组元素转换为小写，并将转换后的值存储到原始数组中。

### 程序

```php
<?php

// Declare an array
$arr = array('GFG', 'GEEK',
        'GEEKS', 'GEEKSFORGEEKS');

$j = 0;

// Iterate loop to convert array
// elements into lowercase and
// overwriting the original array
foreach( $arr as $element ) {
    $arr[$j] = strtolower($element);

$j++;
}

// Display the content of array
foreach( $arr as $element )
    echo $element . "\n";

?>
```

**输出:**

```php
gfg
geek
geeks
geeksforgeeks
```

## 使用 `array_map()` 函数

在这种方法中，`array_map()` 函数用于接受两个参数：回调和一个数组。

### 语法

```php
array array_map( callable callback, array array )
```

这里回调是对数组进行操作时要调用的函数。此函数可以是内置函数或用户定义函数，而数组是要对其执行操作的值列表。

### 程序 2

```php
<?php

// Declare an array
$arr = array('GFG', 'GEEK',
        'GEEKS', 'GEEKSFORGEEKS');

$arr = array_map( 'strtolower', $arr );

// Display the content of array
foreach( $arr as $element )
    echo $element . "\n";

?>
```

**输出:**

```php
gfg
geek
geeks
geeksforgeeks
```