# PHP Imagick setImageGravity() 函数

> Original: [https://www.geeksforgeeks.org/php-imagick-setimagegravity-function/](https://www.geeksforgeeks.org/php-imagick-setimagegravity-function/)

`Imagick::setImageGravity()` 函数是 PHP 中的一个内置函数，用于设置图像的重力属性。`setGravity()` 和 `setImageGravity()` 的区别在于前者应用于整个 `Imagick` 对象，而后者设置序列中当前图像的重力（如果有多个图像）。

## 语法

```php
bool Imagick::setImageGravity( int $gravity )
```

## 参数

此函数接受包含整数值的单个参数 `$gravity`。
重力常数列表如下：

*   `Imagick::GRAVITY_NORTHWEST` (0)
*   `Imagick::GRAVITY_NORTH` (1)
*   `Imagick::GRAVITY_NORTHEAST` (2)
*   `Imagick::GRAVITY_WEST` (3)
*   `Imagick::GRAVITY_CENTER` (4)
*   `Imagick::GRAVITY_EAST` (5)
*   `Imagick::GRAVITY_SOUTHWEST` (6)
*   `Imagick::GRAVITY_SOUTH` (7)
*   `Imagick::GRAVITY_SOUTHEAST` (8)

## 返回值

此函数返回布尔值。

下面的程序演示了 PHP 中的 `Imagick::setImageGravity()` 函数：

## 程序 1

```php
<?php

// Create a new imagick object
$imagick = new Imagick(
'https://media.geeksforgeeks.org/wp-content/uploads/geeksforgeeks-13.png');

// Set the Gravity
$imagick->setImageGravity(7);

// Get the Gravity
$gravity = $imagick->getImageGravity();
echo $gravity;
?>
```

发帖主题：Re：Колибри0.7.0

```php

```

## 程序 2

```php
<?php

// Create a new imagick object
$imagick = new Imagick(
'https://media.geeksforgeeks.org/wp-content/uploads/geeksforgeeks-13.png');

// Set the Gravity
$imagick->setImageGravity(3);

// Get the Gravity
$gravity = $imagick->getImageGravity();
echo $gravity;
?>
```

发帖主题：Re：Колибри0.7.0

```php

```

## 引用

[https://www.php.net/manual/en/imagick.setimagegravity.php](https://www.php.net/manual/en/imagick.setimagegravity.php)