# PHP SplFileObject::rewind() 函数

> Original: [https://www.geeksforgeeks.org/php-splfileobject-rewind-function/](https://www.geeksforgeeks.org/php-splfileobject-rewind-function/)

`SplFileObject::rewind()` 函数是 PHP 中标准 PHP 库 (SPL) 的内置函数，用于将文件指针倒回到第一行。

**语法：**

```php
void SplFileObject::rewind( void )
```

**参数：** 此函数不接受任何参数。

**返回值：** 此函数不返回任何值。

下面的程序说明了 PHP 中的 `SplFileObject::rewind()` 函数：

## Program-1

```php
<?php

// PHP program to illustrate
// SplFileObject::rewind function

$file = new SplFileObject(__FILE__);

$file->rewind();

echo $file->current();
?>
```

## Program-2

```php
<?php

// PHP program to use array to check
// multiple files
$GFG = array(
    "/home/rajvir/Desktop/GeeksforGeeks/dummy.php",
    "gfg.txt",
    "mime.php"
    );

foreach ($GFG as &$file_name) {

    $file = new SplFileObject($file_name);
    $file->rewind();
    echo $file->current();
}
?>
```

**Output:**

```
GeeksforGeeks
gfg
contribute
```

**引用：** [http://php.net/manual/en/splfileobject.rewind.php](http://php.net/manual/en/splfileobject.rewind.php)