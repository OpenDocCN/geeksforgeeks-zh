# PHP `Ds\Map::sorted()` 函数

> 原文：`https://www.geeksforgeeks.org/php-dsmap-sorted-function/`

`Ds\Map::sorted()` 函数是 PHP 中的一个内置函数，用于获取根据值排序的指定 Map 实例的副本。默认情况下，Map 的副本按照值的递增顺序进行排序。

## 语法

```php
public Ds\Map::sorted( $comparator )
```

## 参数

此函数接受单个参数 `$comparator`，该参数包含对映射副本进行排序时将根据其比较值的函数。比较器应根据作为参数传递给它的两个值的比较返回下列值：

*   `1`：如果第一个元素预期小于第二个元素。
*   `-1`：如果第一个元素预期大于第二个元素。
*   `0`：如果第一个元素预期等于第二个元素。

## 返回值

此函数返回根据值排序的 Map 副本。

## 注意

此函数不修改或影响实际的地图实例。

以下程序说明了 PHP 中的 `Ds\Map::sorted()` 函数：

## 程序 1

```php
<?php
// PHP program to illustrate sorted() function

// Declare a Map
$map = new \Ds\Map([1 => 20, 2 => 10, 3 => 30]);

// Print the sorted copy Map
print_r($map->sorted());

?>
```

## 程序 2

```php
<?php
// PHP program to illustrate sorted() function

// Declare a Map
$map = new \Ds\Map([1 => 20, 2 => 10, 3 => 30]);

// Declaring comparator function
$comp = function($first, $second){
        if($first>$second)
            return -1;
        else if($first<$second)
            return 1;
        else 
            return 0;
};

// Print the sorted copy Map
print_r($map->sorted());

?>
```

## 引用

`http://php.net/manual/en/ds-map.sorted.php`