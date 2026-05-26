# FilesystemIterator::__construct() 函数

> Original: [https://www.geeksforgeeks.org/php-filesystemiterator-__construct-function/](https://www.geeksforgeeks.org/php-filesystemiterator-__construct-function/)

`FilesystemIterator::__construct()` 函数是 PHP 中的内置函数，用于构造新的文件系统迭代器。

## 语法

```php
public FilesystemIterator::__construct( string $path, int $flags )
```

## 参数

此函数接受上述两个参数，如下所述：

*   `$path`: 此参数保存文件系统条目的路径。
*   `$flags`: 此参数保存影响某些方法行为的标志。

## 返回值

此函数不返回任何值。

下面的程序演示了 PHP 中的 `FilesystemIterator::__construct()` 函数：

### 程序 1

```php
<?php

// Create new file system iterator
$fileItr = new FilesystemIterator(dirname(__FILE__));

// Loop runs for each element of filesystem
foreach ($fileItr as $file) {

// Display the filename
    echo $file->getFilename() . "<br>";
}
?>
```

### 程序 2

```php
<?php

// Create new file system iterator
$fileItr = new FilesystemIterator(dirname(__FILE__));

// Loop runs while file iterator is valid
while ($fileItr->valid()) {

// Check for directory files
    if ($fileItr->isDir()) {

// Display the file name
        echo $fileItr->getFilename() . "<br>";
    }

// Move to the next element
    $fileItr->next();
}

?>
```

**注意：** 此函数的输出取决于服务器文件夹的内容。

**引用：** [https://www.php.net/manual/en/filesystemiterator.construct.php](https://www.php.net/manual/en/filesystemiterator.construct.php)