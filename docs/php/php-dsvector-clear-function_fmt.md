# PHP|Ds\Vector Clear()函数

> Original: [https://www.geeksforgeeks.org/php-dsvector-clear-function/](https://www.geeksforgeeks.org/php-dsvector-clear-function/)

`Ds\Vector::clear()`函数是 PHP 中的一个内置函数，用于通过从向量中删除所有元素来清除向量元素。

**语法：**

```php
void public Ds\Vector::clear( void )
```

**参数：** 此函数不接受任何参数。

**返回值：** 此函数不返回任何值。

以下程序说明了 PHP 中的 `Ds\Vector::clear()` 函数：

**程序 1：**

```php
<?php

// Create new vector
$vector = new \Ds\Vector([1, 2, 3, 4, 5]);

echo ("Original Vector\n");

// Display vector elements
print_r($vector);

echo("Modified Vector\n");

// Use clear() function to 
// remove vector elements
$vector->clear();

// Display vector elements
print_r($vector);

?>
```

**程序 2：**

```php
<?php

// Create new vector
$vector = new \Ds\Vector(["geeks", "for", "geeks"]);

echo ("Original Vector\n");

// Display vector elements
print_r($vector);

echo("Modified Vector\n");

// Use clear() function to 
// remove vector elements
$vector->clear();

// Display vector elements
print_r($vector);

?>
```

**引用：** [http://php.net/manual/en/ds-vector.clear.php](http://php.net/manual/en/ds-vector.clear.php)