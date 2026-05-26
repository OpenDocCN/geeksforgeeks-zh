# PHP `imagecolorclosest()` 函数

> Original: [https://www.geeksforgeeks.org/php-imagecolorclosest-function/](https://www.geeksforgeeks.org/php-imagecolorclosest-function/)

`imagecolorclosest()` 函数是 PHP 中的一个内置函数，用于获取给定图像中最接近颜色的索引。 此函数用于返回图像调色板中最接近指定 RGB 值的颜色索引。

## 语法

```php
int imagecolorclosest( $image, $red, $green, $blue )
```

## 参数

此函数接受上述四个参数，如下所述：

*   `$image`: 由图像创建函数（如 `imagecreatetruecolor()`）返回，用于指定图像。
*   `$red`: 用于设置红色分量的值。
*   `$green`: 用于设置绿色分量的值。
*   `$blue`: 用于设置蓝色分量的值。

## 返回值

此函数返回图像调色板中最接近颜色的索引。

下面的程序演示了 PHP 中的 `imagecolorclosest()` 函数。

### 程序 1

```php
<?php

// Start with an image and convert it to a palette-based image
$image = imagecreatefrompng(
'https://media.geeksforgeeks.org/wp-content/uploads/geeks-21.png');

imagetruecolortopalette($image, false, 255);

//  Search closest color
$result = imagecolorclosest($image, 7, 150, 10);

$result = imagecolorsforindex($image, $result);

$result = "({$result['red']}, {$result['green']}, {$result['blue']})";

echo "Closest color: " . $result;

imagedestroy($image);

?>
```

### 程序 2

```php
<?php

// Start with an image and convert it to a palette-based image
$image = imagecreatefrompng(
'https://media.geeksforgeeks.org/wp-content/uploads/geeks-21.png');

imagetruecolortopalette($image, false, 255);

// Search RGB colors
$color = array(
    array(7, 150, 0),
    array(53, 190, 255),
    array(255, 165, 54)
);

// Loop to find the closest color to the given RGB color
foreach($color as $id => $rgb)
{
    $result = imagecolorclosest($image, $rgb[0], $rgb[1], $rgb[2]);
    $result = imagecolorsforindex($image, $result);
    $result = "({$result['red']}, {$result['green']}, {$result['blue']})";

echo "Given color: ($rgb[0], $rgb[1], $rgb[2]) => Closest match: $result<br>";
}

imagedestroy($image);

?>
```

## 相关函数

*   [`getimagesize()` 函数](https://www.geeksforgeeks.org/php-getimagesize-function/)
*   [`imageflip()` 函数](https://www.geeksforgeeks.org/php-imageflip-function/)
*   [`imagesx()` 函数](https://www.geeksforgeeks.org/php-imagesx-function/)

## 引用

[http://php.net/manual/en/function.imagecolorclosest.php](http://php.net/manual/en/function.imagecolorclosest.php)