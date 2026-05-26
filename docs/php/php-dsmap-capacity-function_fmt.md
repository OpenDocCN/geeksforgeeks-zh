# PHP `Ds\Map::capacity()` 函数

> 原文：[https://www.geeksforgeeks.org/php-dsmap-capacity-function/](https://www.geeksforgeeks.org/php-dsmap-capacity-function/)

`Ds\Map::capacity()` 函数是 PHP 中的内置函数，用于返回 Map 的当前容量。

## 语法

```php
int public Ds\Map::capacity( void )
```

## 参数

此函数不接受任何参数。

## 返回值

此函数返回 Map 当前的容量。

## 示例

下面的程序演示了 PHP 中的 `Ds\Map::capacity()` 函数：

```php
<?php

// Declare a map 
$map = new \Ds\Map();

// Use capacity() function 
var_dump($map->capacity());

// Creating a Map 
$map = new \Ds\Map(["1" => "Geeks",   
            "2" => "for", "3" => "Geeks"]);

// Use capacity() function 
var_dump($map->capacity());

?>
```

**输出：**

```
int(8)
int(8)
```

## 引用

[https://www.php.net/manual/en/ds-map.capacity.php](https://www.php.net/manual/en/ds-map.capacity.php)