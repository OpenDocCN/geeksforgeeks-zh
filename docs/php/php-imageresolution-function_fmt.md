# PHP `imageresolution()` 函数

> Original: [https://www.geeksforgeeks.org/php-imageresolution-function/](https://www.geeksforgeeks.org/php-imageresolution-function/)

`imageresolution()` 函数是 PHP 中的内置函数，用于设置和返回 DPI(每英寸点数)格式的图像分辨率。 如果没有给出任何可选参数，则当前分辨率以索引数组的形式返回。 如果给出了一个可选参数，它将同时设置该参数的宽度和高度。 只有在从支持此类信息的格式(当前为 PNG 和 JPEG)中读取和写入图像时，分辨率才用作元信息。 它不会影响图像的外观。 新图像的默认分辨率为 96 DPI。

## 语法

```php
imageresolution( $image, $res_x, $res_y )
```

## 参数

此函数接受三个参数，如下所述：

*   `$image`: 指定要处理的图像资源。
*   `$res_x` (可选): 指定水平分辨率（DPI）。
*   `$res_y` (可选): 指定垂直分辨率（DPI）。

## 返回值

此函数用作 getter 时返回索引数组，用作 setter 时返回 `true`，失败时返回 `false`。

## 示例

下面的示例说明了 PHP 中的 `imageresolution()` 函数：

### 示例 1

在此示例中，我们将获得图像的分辨率。

```php
<?php

// Load the png image
$image = imagecreatefrompng(
'https://media.geeksforgeeks.org/wp-content/uploads/geeksforgeeks-13.png');

// Get the image resolution
$imageresolution = imageresolution($image);
print("<pre>".print_r($imageresolution, true)."</pre>");
?>
```

### 示例 2

在此示例中，我们将设置图像的分辨率。

```php
<?php

// Load the png image
$image = imagecreatefrompng(
'https://media.geeksforgeeks.org/wp-content/uploads/geeksforgeeks-13.png');

// Set the resolution
imageresolution($image, 400, 200);

// Get the image resolution
$imageresolution = imageresolution($image);
print("<pre>".print_r($imageresolution, true)."</pre>");
?>
```

## 引用

[https://www.php.net/manual/en/function.imageresolution.php](https://www.php.net/manual/en/function.imageresolution.php)