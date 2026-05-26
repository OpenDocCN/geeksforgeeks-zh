# PHP Imagick setImageProperty() 函数

> Original: [https://www.geeksforgeeks.org/php-imagick-setimageproperty-function/](https://www.geeksforgeeks.org/php-imagick-setimageproperty-function/)

`Imagick::setImageProperty()` 函数是 PHP 中的内置函数，用于设置 image 属性。图像属性和图像工件之间的主要区别在于属性是公共的，而工件是私有的。

## 语法

```php
bool Imagick::setImageProperty( string $name, string $value )
```

## 参数

此函数接受上述两个参数，如下所述：

*   `$name`: 此参数保存属性的名称。
*   `$value`: 此参数保存属性的值。

## 返回值

如果成功，此函数返回 `TRUE`。

下面的程序演示了 PHP 中的 `Imagick::setImageProperty()` 函数：

## 程序

```php
<?php

// Create a new Imagick object
$imagick = new Imagick(
'https://media.geeksforgeeks.org/wp-content/uploads/geeksforgeeks-9.png');

// Apply the setImageProperty() function
$imagick->setImageProperty("property_name", "property_value");

// Apply the getImageProperty() function
$property_name = $imagick->getImageProperty("property_name");
echo $property_name;
?>
```

**引用：**[https://www.php.net/manual/en/imagick.setimageproperty.php](https://www.php.net/manual/en/imagick.setimageproperty.php)