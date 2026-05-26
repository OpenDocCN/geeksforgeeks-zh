# PHP GmagickDraw::gettextdecoration() 函数

> Original: [https://www.geeksforgeeks.org/php-gmagickdraw-gettextdecoration-function/](https://www.geeksforgeeks.org/php-gmagickdraw-gettextdecoration-function/)

`GmagickDraw::gettextdecoration()` 函数是 PHP 中的一个内置函数，用于在使用文本进行批注时应用修饰。

## 语法

```php
*int* GmagickDraw::gettextdecoration( *void* )
```

## 参数

此函数不接受任何参数。

## 返回值

此函数返回与其中一个装饰常量对应的整数值。装饰常量列表如下：

*   `Gmagick::DECORATION_NO` (0)
*   `Gmagick::DECORATION_UNDERLINE` (1)
*   `Gmagick::DECORATION_OVERLINE` (2)
*   `Gmagick::DECORATION_LINETHROUGH` (3)

## 异常

此函数在出错时引发 `GmagickDrawException`。

下面给出的程序演示了 PHP 中的 `GmagickDraw::gettextdecoration()` 函数：

## 程序 1

```php
<?php

// Create a new GmagickDraw object 
$draw = new GmagickDraw();

// Get the text decoration 
$textDecoration = $draw->gettextdecoration(); 
echo $textDecoration; 
?>
```

输出：
```
0 // Which is the default value
```

## 程序 2

```php
<?php

// Create a new GmagickDraw object 
$draw = new GmagickDraw();

// Set the text decoration
$draw->settextdecoration(3);

// Get the text decoration 
$textDecoration = $draw->gettextdecoration(); 
echo $textDecoration; 
?>
```

输出：
```
3
```

## 已用图像

![](img/07c99ec29e7a50fc3ea91a9d4a8d2f31.png)

## 程序 3

```php
<?php

// Create a new Gmagick object
$gmagick = new Gmagick('geeksforgeeks.png');

// Create a GmagickDraw object
$draw = new GmagickDraw();

// Set the color
$draw->setFillColor('#0E0E0E');

// Draw rectangle for background
$draw->rectangle(-10, -10, 800, 400);

// Set the font size
$draw->setfontsize(30);

// Set the fill color
$draw->setFillColor('white');

// Set the text decoration to overline
$draw->settextdecoration(2);

// Get the text decoration
$textDecoration = $draw->gettextdecoration();

// Annotate a text
$draw->annotate(50, 100, 'The text decoration here is '
    . $textDecoration);

// Use of drawimage function
$gmagick->drawImage($draw);

// Display the output image
header("Content-Type: image/png");
echo $gmagick->getImageBlob();
?>
```

输出：
![](img/5d8495db43cc498b7562297a8824b312.png)

## 引用

[https://www.php.net/manual/en/gmagickdraw.gettextdecoration.php](https://www.php.net/manual/en/gmagickdraw.gettextdecoration.php)