# PHP Ds\Map allocate() 函数

> Original: [https://www.geeksforgeeks.org/php-dsmap-allocate-function/](https://www.geeksforgeeks.org/php-dsmap-allocate-function/)

`Ds\Map::allocate()` 函数是 PHP 中的一个内置函数，用于为所需的容量分配足够的内存。

## 语法

```php
void public Ds\Map::allocate( $capacity )
```

## 参数

此函数接受单个参数 `$capacity`，表示分配的容量数量。

## 返回值

此函数不返回任何值。

下面的程序说明了 PHP 中的 `Ds\Map::allocate()` 函数：

## 程序 1

```php
<?php

// Create new map
$map = new \Ds\Map();

// Use capacity() function to
// display the capacity of map
var_dump($map->capacity());

// Allocate capacity
$map->allocate(50);

// Display capacity
var_dump($map->capacity());

// Allocate capacity
$map->allocate(80);

// Display capacity
var_dump($map->capacity());
?>
```

## 输出

```php
int(8)
int(64)
int(128)
```

## 程序 2

```php
<?php

// Create new map
$map = new \Ds\Map();

// Declare capacity array
$arr = array(10, 20, 30, 40);

// Loop run for every array element
foreach ($arr as $val) {

    // Allocate capacity
    $map->allocate($val);

    // Display capacity of map
    var_dump($map->capacity());
}

?>
```

## 输出

```php
int(16)
int(32)
int(32)
int(64)
```

**引用：**[https://www.php.net/manual/en/ds-map.allocate.php](https://www.php.net/manual/en/ds-map.allocate.php)