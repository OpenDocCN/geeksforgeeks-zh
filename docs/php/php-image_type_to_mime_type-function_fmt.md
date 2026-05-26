# PHP `image_type_to_mime_type()` 函数

> Original: [https://www.geeksforgeeks.org/php-image_type_to_mime_type-function/](https://www.geeksforgeeks.org/php-image_type_to_mime_type-function/)

`image_type_to_mime_type()` 函数是 PHP 中的内置函数，用于获取由其他不同函数返回的 `imageType` 的 `MimeType`，如 `getimagesize()`、`exif_read_data()`、`exif_thumbnail()`、`exif_imagetype()` 等。
**MIME** 代表 **多用途 Internet 邮件扩展**。 MIME 类型表单是对 Internet 上的文件类型进行分类的标准方式。 诸如 Web 服务器和浏览器之类的 Internet 程序都有 MIME 类型列表，因此它们可以以相同的方式传输相同类型的文件，无论它们运行的是哪种操作系统。

## 语法

```php
string image_type_to_mime_type( int $imagetype )
```

## 参数

此函数接受单个参数 `$imageType`，该参数保存 `imageType_XXX` 常量（如 `IMAGETYPE_GIF`、`IMAGETYPE_JPEG`、`IMAGETYPE_PNG` 等）的整数值。

## 返回值

此函数返回给定 `imageType` 常量的 Mime 类型字符串。

下面是所有返回值的详尽列表。

| 图像类型 | 返回值 |
| --- | --- |
| `IMAGETYPE_GIF` | `image/gif` |
| `IMAGETYPE_JPEG` | `image/jpeg` |
| `IMAGETYPE_PNG` | `image/png` |
| `IMAGETYPE_SWF` | `application/x-shockwave-flash` |
| `IMAGETYPE_PSD` | `image/psd` |
| `IMAGETYPE_BMP` | `image/bmp` |
| `IMAGETYPE_TIFF_II` (Intel 字节顺序) | `image/tiff` |
| `IMAGETYPE_TIFF_MM` (Motorola 字节顺序) | `image/tiff` |
| `IMAGETYPE_JPC` | `application/octet-stream` |
| `IMAGETYPE_JP2` | `image/jp2` |
| `IMAGETYPE_JPX` | `application/octet-stream` |
| `IMAGETYPE_JB2` | `application/octet-stream` |
| `IMAGETYPE_SWC` | `application/x-shockwave-flash` |
| `IMAGETYPE_IFF` | `image/iff` |
| `IMAGETYPE_WBMP` | `image/vnd.wap.wbmp` |
| `IMAGETYPE_XBM` | `image/xbm` |
| `IMAGETYPE_ICO` | `image/vnd.microsoft.icon` |
| `IMAGETYPE_WEBP` | `image/webp` |

下面的程序演示了 PHP 中的 `image_type_to_mime_type()` 函数：

### 程序 1

```php
<?php
echo image_type_to_mime_type(IMAGETYPE_PNG);
?>
```

输出：
```
image/png
```

### 程序 2

```php
<?php
echo image_type_to_mime_type(IMAGETYPE_JPEG);
?>
```

输出：
```
image/jpeg
```

**引用：** [https://www.php.net/manual/en/function.image-type-to-mime-type.php](https://www.php.net/manual/en/function.image-type-to-mime-type.php)