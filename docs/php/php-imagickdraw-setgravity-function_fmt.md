# PHP ImagickDraw::setGravity() 函数

> 原文：[https://www.geeksforgeeks.org/php-imagickdraw-setgravity-function/](https://www.geeksforgeeks.org/php-imagickdraw-setgravity-function/)

`ImagickDraw::setGravity()` 函数是 PHP 中的一个内置函数，用于在使用文本进行注释时设置文本放置的重力（对齐方向）。

## 语法

```php
bool ImagickDraw::setGravity( $gravity )
```

## 参数

此函数接受单个参数 `$gravity`，该参数用于将重力值设置为预定义的重力常量。

重力常量列表如下：

*   `Imagick::GRAVITY_NORTHWEST` (整数)
*   `Imagick::GRAVITY_NORTH` (整数)
*   `Imagick::GRAVITY_NORTHEAST` (整数)
*   `Imagick::GRAVITY_WEST` (整数)
*   `Imagick::GRAVITY_CENTER` (整数)
*   `Imagick::GRAVITY_EAST` (整数)
*   `Imagick::GRAVITY_SOUTHWEST` (整数)
*   `Imagick::GRAVITY_SOUTH` (整数)
*   `Imagick::GRAVITY_SOUTHEAST` (整数)

## 返回值

此函数不返回任何值。

## 示例

下面的程序演示了 PHP 中的 `ImagickDraw::setGravity()` 函数：

### 程序 1

```php
<?php

// 创建一个 ImagickDraw 对象
$draw = new ImagickDraw();

// 设置图像填充颜色
$draw->setFillColor('Green');

// 设置字体大小
$draw->setFontSize(30);

// 设置重力位置
$draw->setGravity(5);

// 设置字体族
$draw->setFontFamily('Ani');

// 设置要添加的文本
$draw->annotation(30, 40, "GeeksForGeeks");

// 创建新的 Imagick 对象
$imagick = new Imagick();

// 设置图像尺寸
$imagick->newImage(300, 150, 'white');

// 设置图像格式
$imagick->setImageFormat("png");

// 绘制图像
$imagick->drawImage($draw);
header("Content-Type: image/png");

// 显示图像
echo $imagick->getImageBlob();
?>
```

**输出：**
![setGravity](img/f3e4cbca3ad154972cd09e53acc19daa.png)

### 程序 2

```php
<?php

// 创建一个 ImagickDraw 对象
$draw = new ImagickDraw();

// 设置图像填充颜色
$draw->setFillColor('green');

// 设置字体大小
$draw->setFontSize(60);

// 设置重力位置
$draw->setGravity(2);

// 设置文本装饰
$draw->setTextDecoration(4);

// 设置要添加的文本
$draw->annotation(50, 75, "GeeksForGeeks");

// 创建新的 Imagick 对象
$imagick = new Imagick();

// 设置图像尺寸
$imagick->newImage(600, 160, 'white');

// 设置图像格式
$imagick->setImageFormat("png");

// 绘制图像
$imagick->drawImage($draw);
header("Content-Type: image/png");

// 显示图像
echo $imagick->getImageBlob();
?>
```

**输出：**
![setGravity](img/67f1556c868ec62de88ff63e2c763c67.png)

## 引用

[http://php.net/manual/en/imagickdraw.setgravity.php](http://php.net/manual/en/imagickdraw.setgravity.php)