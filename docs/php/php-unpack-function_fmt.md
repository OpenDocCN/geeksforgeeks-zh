# PHP unpack() 函数

> Original: [https://www.geeksforgeeks.org/php-unpack-function/](https://www.geeksforgeeks.org/php-unpack-function/)

`unpack()`函数是 PHP 中的一个内置函数，用于将二进制字符串解压缩为相应的格式。

## 语法：

```php
array unpack( $format, $data, $offset )
```

## 参数：

此函数接受上述三个参数，如下所述：

*   `$format`: 必需参数。它指定打包数据时使用的格式。
    *   `A-` 表示无填充的字符串。
    *   `A-` 表示用空格填充的字符串。
    *   `H-` 表示低半字节的第一个十六进制字符串。
    *   `H-` 表示高半字节的第一个十六进制字符串。
    *   `C-` 表示有符号字符。
    *   `C-` 表示无符号字符。
    *   `S-` 表示有符号短代码（16位，机器字节序）。
    *   `S-` 表示无符号短代码（16位，机器字节序）。
    *   `N-` 表示无符号短代码（16位，大端字节序）。
    *   `V-` 表示无符号短代码（16位，小端字节序）。
    *   `I-` 表示有符号整数（字节序和大小与机器相关）。
    *   `I-` 表示无符号整数（字节序和大小与机器相关）。
    *   `L-` 表示有符号长整数（32位，机器字节序）。
    *   `L-` 表示无符号长整数（32位，机器字节序）。
    *   `N-` 表示无符号长度（32位，大端字节序）。
    *   `V-` 表示无符号长度（32位，小端字节序）。
    *   `F-` 表示浮点数（表示和大小与机器相关）。
    *   `D-` 表示双精度（表示和大小与机器相关）。
    *   `X-` 表示 NUL 字节。
    *   `X-` 表示回退一个字节。
    *   `Z-` 表示无填充的字符串。
    *   `@-` 表示填充 NUL 到绝对位置。
*   `$data`: 必需参数。它指定要解包的二进制数据。
*   `$offset`: 此参数保存从解包开始的偏移量。

## 返回值：

成功时返回包含解包元素的关联数组，失败时返回 `False`。

## 注意：

此函数适用于 PHP 4.0.0 及更新版本。

## 示例 1：

此程序使用 `C` 格式将数据从二进制字符串解包。

```php
<?php

var_dump( unpack("C*", "GEEKSFORGEEKS"));
?>
```

**输出：**

```php
array(13) {
  [1]=>
  int(71)
  [2]=>
  int(69)
  [3]=>
  int(69)
  [4]=>
  int(75)
  [5]=>
  int(83)
  [6]=>
  int(70)
  [7]=>
  int(79)
  [8]=>
  int(82)
  [9]=>
  int(71)
  [10]=>
  int(69)
  [11]=>
  int(69)
  [12]=>
  int(75)
  [13]=>
  int(83)
}
```

## 示例 2：

```php
<?php

$binary_data = pack("c2n2", 0x1634, 0x3623, 65, 66);
var_dump(unpack("c2chars/n2int", $binary_data));
?>
```

**输出：**

```php
array(4) {
  ["chars1"]=>
  int(52)
  ["chars2"]=>
  int(35)
  ["int1"]=>
  int(65)
  ["int2"]=>
  int(66)
}
```

## 示例 3：

此示例使用 `I` 格式将数据从二进制字符串解包。

```php
<?php

$binary_data = pack("i3", 56, 49, 54);
var_dump(unpack("i3", $binary_data));
?>
```

**输出：**

```php
array(3) {
  [1]=>
  int(56)
  [2]=>
  int(49)
  [3]=>
  int(54)
}
```

## 引用：

[https://www.php.net/manual/en/function.unpack.php](https://www.php.net/manual/en/function.unpack.php)