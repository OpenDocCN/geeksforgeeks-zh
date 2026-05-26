# PHP GmagickDraw::setTextDecoration() 函数

> Original: [https://www.geeksforgeeks.org/php-gmagickdraw-settextdecoration-function/](https://www.geeksforgeeks.org/php-gmagickdraw-settextdecoration-function/)

`GmagickDraw::setTextDecoration()` 函数是 PHP 中的一个内置函数，用于指定在使用文本进行批注时要应用的修饰。

## 语法

```php
public GmagickDraw::setTextDecoration( $decoration ) : GmagickDraw
```

## 参数

此函数接受单个参数 `$decoration`，该参数用于保存 `DECORATION_*` 常量的值。装饰常量列表如下：

*   `Gmagick::DECORATION_NONE` (integer)
*   `Gmagick::DECORATION_UNDERLINE` (integer)
*   `Gmagick::DECORATION_OVERLINE` (integer)
*   `Gmagick::DECORATION_LINETROUGH` (integer)

## 返回值

此函数在成功时返回 `GmagickDraw` 对象。

下面的程序演示了 PHP 中的 `GmagickDraw::setTextDecoration()` 函数：

## 程序 1

```php
<?php

// Create an GmagickDraw object
$draw = new GmagickDraw ();

// Set the image filled color
$draw->setFillColor('green');

// Set the font size
$draw->setFontSize(60);

// Set the Text Decoration
$draw->setTextDecoration(4);

// Set the text to be added
$draw->annotation(50, 75, "GeeksForGeeks");

// Create new Gmagick Object
$gmagick = new Gmagick ();

// Set image dimensions
$gmagick->newImage(500, 160, 'white');

// Set the image format
$gmagick->setImageFormat("png");

// Draw the image
$gmagick->drawImage($draw);
header("Content-Type: image/png");

// Display the image
echo $gmagick->getImageBlob();
?>
```

**输出：**
![setTextDecoration](img/17d44b1e44a161e375cb910d0ba9f4d2.png)

## 程序 2

```php
<?php

// Create an GmagickDraw object
$draw = new GmagickDraw ();

// Set the image filled color
$draw->setFillColor('yellow');

// Set the font size
$draw->setFontSize(20);

// Set the TextDecoration() function
// Text is Upperline
$draw->setTextDecoration(3);
// Set the text to be added
$draw->annotation(50, 75, "A Computer Science Portal For Geeks!");

// Create new Gmagick Object
$gmagick = new Gmagick ();

// Set the image dimensions
$gmagick->newImage(500, 160, 'black');

// Set the image format
$gmagick->setImageFormat("png");

// Draw the image
$gmagick->drawImage($draw);
header("Content-Type: image/png");

// Display the image
echo $gmagick->getImageBlob();
?>
```

**输出：**
![setTextDecoration](img/7bd49066a15f76c45ba421e45f723a07.png)

**引用：**[http://php.net/manual/en/gmagickdraw.settextdecoration.php](http://php.net/manual/en/gmagickdraw.settextdecoration.php)