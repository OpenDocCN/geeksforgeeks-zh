# PHP ImagickKernel::separate() 函数

> Original: [https://www.geeksforgeeks.org/php-imagickkernel-separate-function/](https://www.geeksforgeeks.org/php-imagickkernel-separate-function/)

`ImagickKernel::separate()` 函数是 PHP 中的一个内置函数，用于分隔一组链接的内核，并返回 `ImagickKernel` 数组。 此函数用于计算对象中的内核或查看对象的内核。

## 语法

```php
array ImagickKernel::separate( void )
```

## 参数

此函数不接受任何参数。

## 返回值

此函数返回包含 `ImagickKernel` 的数组值。

下面的程序演示了 PHP 中的 `ImagickKernel::separate()` 函数：

### 程序 1：对 ImagickKernel 中的所有内核进行计数

```php
<?php

// Create a new imagick object
$imagick = new Imagick(
'https://media.geeksforgeeks.org/wp-content/uploads/geeksforgeeks-13.png');

$matrix1 = [
    [-1, -1, -1],
    [4, 4, 4],
    [1, 1, 1],
];

$matrix2 = [
    [-1, 0, 0],
    [0, 0, 1],
    [-1, 0, 1],
];

$matrix3 = [
    [-1, 1, 0],
    [0, 0, 1],
    [-1, 0, 1],
];

$matrix4 = [
    [0, 1, 0],
    [0, 0, 1],
    [-1, 0, 1],
];

// Create ImagickKernel objects from matrices
$kernel1 = ImagickKernel::fromMatrix($matrix1);
$kernel2 = ImagickKernel::fromMatrix($matrix2);
$kernel3 = ImagickKernel::fromMatrix($matrix3);
$kernel4 = ImagickKernel::fromMatrix($matrix4);

// Add the kernels
$kernel1->addKernel($kernel2);
$kernel1->addKernel($kernel3);
$kernel1->addKernel($kernel4);

$kernelList = $kernel1->separate();

echo 'Total number of attached kernels are: ';
echo count($kernelList);
?>
```

### 程序 2：获取对象中的所有 ImagickKernel

```php
<?php

// Create a new imagick object
$imagick = new Imagick(
'https://media.geeksforgeeks.org/wp-content/uploads/geeksforgeeks-13.png');

$matrix1 = [
    [-1, -1, -1],
    [4, 4, 4],
    [1, 1, 1],
];

$matrix2 = [
    [-1, 0, 0],
    [0, 0, 1],
    [-1, 0, 1],
];

// Create ImagickKernel objects from matrices
$kernel1 = ImagickKernel::fromMatrix($matrix1);
$kernel2 = ImagickKernel::fromMatrix($matrix2);

// Add the kernel
$kernel1->addKernel($kernel2);

$kernelList = $kernel1->separate();

echo 'All the kernels are: ';
print("<pre>".print_r($kernelList, true)."</pre>");
?>
```

**引用：**[https://www.php.net/manual/en/imagickkernel.separate.php](https://www.php.net/manual/en/imagickkernel.separate.php)