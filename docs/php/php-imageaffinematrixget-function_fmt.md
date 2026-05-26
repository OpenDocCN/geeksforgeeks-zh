# PHP `imageaffinematrixget()` 函数

> Original: [https://www.geeksforgeeks.org/php-imageaffinematrixget-function/](https://www.geeksforgeeks.org/php-imageaffinematrixget-function/)

函数的作用是：获取仿射变换矩阵。仿射是一种涉及矩阵的几何变换运算，通常用于线性代数和计算机图形学。

## 语法

```php
array imageaffinematrixget( int $type, mixed $options )
```

## 参数

此函数接受上述两个参数，如下所述：

*   `$type`：它指定与 [img_affine 常量](https://www.php.net/manual/en/image.constants.php#constant.img-affine-translate) 之一相对应的整数。
    所有 img_affine 常量列表如下：
    *   `IMG_AFFINE_TRANSLATE` (0)
    *   `IMG_AFFINE_SCALE` (1)
    *   `IMG_AFFINE_ROTATE` (2)
    *   `IMG_AFFINE_SHEAR_HORIZONTAL` (3)
    *   `IMG_AFFINE_SHEAR_VERTICAL` (4)
*   `$options`：指定要转换为数组的选项，可以是数组，也可以是浮点数。

## 返回值

此函数在失败时返回仿射变换矩阵（具有 0 到 5 个键和浮点值的数组）或 `False`。

## 示例

下面给出的程序说明了 PHP 中的 `imageaffinematrixget()` 函数：

### 程序 1（从数组创建）

```php
<?php
// Create an array
$arr = array('x' => 5, 'y' => 8);

// Get the image affine matrix
$matrix = imageaffinematrixget(IMG_AFFINE_TRANSLATE, $arr);

// Output the matrix
print("<pre>".print_r($matrix, true)."</pre>");
?>
```

**输出：**

```
Array
(
    [0] => 1
    [1] => 0
    [2] => 0
    [3] => 1
    [4] => 5
    [5] => 8
)
```

### 程序 2（从角度创建）

```php
<?php
// Create an angle
$angle = 300;

// Get the image affine matrix
$matrix = imageaffinematrixget(IMG_AFFINE_SHEAR_HORIZONTAL, $angle);

// Output the matrix
print("<pre>".print_r($matrix, true)."</pre>");
?>
```

**输出：**

```
Array
(
    [0] => 1
    [1] => 0
    [2] => -1.7320508075689
    [3] => 1
    [4] => 0
    [5] => 0
)
```

## 引用

[https://www.php.net/manual/en/function.imageaffinematrixget.php](https://www.php.net/manual/en/function.imageaffinematrixget.php)