# PHP Imagick扩展：addNoiseImage()函数

> Original: [https://www.geeksforgeeks.org/php-imagickaddnoiseimage-function/](https://www.geeksforgeeks.org/php-imagickaddnoiseimage-function/)

`Imagick::addNoiseImage()`函数是PHP中的一个内置函数，用于在给定图像中添加噪声。噪波的强度取决于噪波常数和通道类型。图像噪声是图像中亮度和对比度的随机变化。

**语法：**

```php
bool Imagick::addNoiseImage ( $noise_type, $channel )
```

**参数：**此函数接受上述两个参数，如下所述：

*   `$noise_type`: 此参数用于设置噪声类型。`Imagick`函数中提供了一些噪声常量，如下所示：
    *   `Imagick::NOISE_UNIFORM`
    *   `Imagick::NOISE_GAUSSIAN`
    *   `Imagick::NOISE_MULTIPLICATIVE_GAUSSIAN`
    *   `Imagick::NOISE_IMPULSE`
    *   `Imagick::NOISE_LAPLACIAN`
    *   `Imagick::NOISE_POISSON`
    *   `Imagick::NOISE_RANDOM`

ImageMagick版本6.3.6及更高版本支持此常量。

*   `$channel`: 此参数提供通道常量。可以使用按位运算符组合两个或更多个通道。`Imagick`函数中有一些通道常量可用，如下所示：
    *   `Imagick::CHANNEL_UNDEFINED`
    *   `Imagick::CHANNEL_RED`
    *   `Imagick::CHANNEL_GRAY`
    *   `Imagick::CHANNEL_CYAN`
    *   `Imagick::CHANNEL_GREEN`
    *   `Imagick::CHANNEL_MAGENTA`
    *   `Imagick::CHANNEL_BLUE`
    *   `Imagick::CHANNEL_YELLOW`
    *   `Imagick::CHANNEL_ALPHA`
    *   `Imagick::CHANNEL_OPACITY`
    *   `Imagick::CHANNEL_MOMENTS`
    *   `Imagick::CHANNEL_BLACK`
    *   `Imagick::CHANNEL_COMPOSITE`
    *   `Imagick::CHANNEL_ALL`
    *   `Imagick::CHANNEL_DEFAULT`

**返回值：**如果成功，此函数返回`TRUE`。

下面的程序演示了PHP中的`Imagick::addNoiseImage()`函数：

**原图：**
![original image](img/c6e0a168008bc4a43314f9fb895e5c7c.png)

**程序：**

```php
<?php

// require_once('path/to/vendor/autoload.php');

header('Content-type: image/png');

$image = new Imagick(
'https://media.geeksforgeeks.org/wp-content/uploads/geeksforgeeks-9.png');

$image->addNoiseImage(3, imagick::CHANNEL_DEFAULT);

echo $image;
?>
```

**输出：**
![](img/a0edfca835cba3ccfe8c6309dda65d17.png)

**引用：**[http://php.net/manual/en/imagick.addnoiseimage.php](http://php.net/manual/en/imagick.addnoiseimage.php)