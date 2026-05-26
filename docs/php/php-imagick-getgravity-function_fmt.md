# Imagick::getGravity() 函数

> Original: [https://www.geeksforgeeks.org/php-imagick-getgravity-function/](https://www.geeksforgeeks.org/php-imagick-getgravity-function/)

## 函数介绍

`Imagick::getGravity()` 函数是 PHP 中的一个内置函数，用于获取 `Imagick` 对象的全局重力属性。

## 语法

```php
int Imagick::getGravity( void )
```

## 参数

此函数不接受任何参数。

## 异常

此函数在出错时引发 `ImagickException`。

## 返回值

此函数返回表示重力常数的整数值。重力常数列表如下：

*   `Imagick::GRAVITY_NORTHWEST(1)`
*   `Imagick::GRAVITY_NORTH(2)`
*   `Imagick::GRAVITY_NORTHEAST(3)`
*   `Imagick::GRAVITY_WEST(4)`
*   `Imagick::GRAVITY_CENTER(5)`
*   `Imagick::GRAVITY_EAST(6)`
*   `Imagick::GRAVITY_SOUTHWEST(7)`
*   `Imagick::GRAVITY_SOUTH(8)`
*   `Imagick::GRAVITY_SOUTHEAST(9)`

## 示例

下面的程序演示了 PHP 中的 `Imagick::getGravity()` 函数：

### 程序 1

```php
<?php

// Create a new imagick object
$imagick = new Imagick();

// Get the Gravity
$gravity = $imagick->getGravity();

echo $gravity;
?>
```

发帖主题：Re：Колибри0.7.0

```
0 // Which means gravity is not set.
```

### 程序 2

```php
<?php

// Create a new imagick object
$imagick = new Imagick('https://media.geeksforgeeks.org/wp-content/uploads/geeksforgeeks-13.png');

// Set the Gravity
$imagick->setGravity(3);

// Get the Gravity
$gravity = $imagick->getGravity();

echo $gravity;
?>
```

发帖主题：Re：Колибри0.7.0

```
3 // Which corresponds to Imagick::GRAVITY_NORTHEAST.
```

## 引用

[https://www.php.net/manual/en/imagick.getgravity.php](https://www.php.net/manual/en/imagick.getgravity.php)