# PHP `Ds\Vector::slice()` 函数

> 原文：[https://www.geeksforgeeks.org/php-dsvector-slice-function/](https://www.geeksforgeeks.org/php-dsvector-slice-function/)

## 简介

`Ds\Vector::slice()` 函数是 PHP 中的一个内置函数，用于返回给定向量的子向量。

## 语法

```php
public Ds\Vector::slice( $index, $length )
```

## 参数

此函数接受两个参数，描述如下：

*   `$index`：此参数保存子向量的起始索引。索引值可以是正的，也可以是负的。如果索引值为正，则从向量的该索引处开始；如果索引值为负，则从结束处开始。
*   `$length`：此参数保存子向量的长度。此参数可以采用正值和负值。如果长度为正，则子向量大小等于给定长度；如果长度为负，则向量将从末尾停止那么多值。

## 返回值

此函数返回给定范围的子向量。

## 示例

以下程序演示了 PHP 中的 `Ds\Vector::slice()` 函数：

### 程序 1

```php
<?php

// Create new vector 
$vect = new \Ds\Vector([1, 2, 3, 4, 5, 6]);

echo("Original vector:\n");

// Display the vector element 
var_dump($vect);

// Use slice() function to  
// create sub vector 
$res = $vect->slice(1, 2);

echo("\nNew sub-vector\n");

// Display the sub-vector elements 
var_dump($res);

?> 
```

**输出：**

```
Original vector:
object(Ds\Vector)#1 (6) {
  [0]=>
  int(1)
  [1]=>
  int(2)
  [2]=>
  int(3)
  [3]=>
  int(4)
  [4]=>
  int(5)
  [5]=>
  int(6)
}

New sub-vector
object(Ds\Vector)#2 (2) {
  [0]=>
  int(2)
  [1]=>
  int(3)
}
```

### 程序 2

```php
<?php

// Create new vector
$vect = new \Ds\Vector([1, 2, 3, 4, 5, 6]);

echo("Original vector:\n");

// Display the vector element
var_dump($vect);

// Use slice() function to 
// create sub vector
$res = $vect->slice(2, -2);

echo("\nNew sub-vector\n");

// Display the sub-vector elements
var_dump($res);

$res = $vect->slice(4);

echo("\nNew sub-vector\n");

// Display the sub-vector elements
var_dump($res);

?>
```

**输出：**

```
Original vector:
object(Ds\Vector)#1 (6) {
  [0]=>
  int(1)
  [1]=>
  int(2)
  [2]=>
  int(3)
  [3]=>
  int(4)
  [4]=>
  int(5)
  [5]=>
  int(6)
}

New sub-vector
object(Ds\Vector)#2 (2) {
  [0]=>
  int(3)
  [1]=>
  int(4)
}

New sub-vector
object(Ds\Vector)#3 (2) {
  [0]=>
  int(5)
  [1]=>
  int(6)
}
```

## 引用

[http://php.net/manual/en/ds-vector.slice.php](http://php.net/manual/en/ds-vector.slice.php)