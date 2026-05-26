# PHP SplFileInfo::getGroup() 函数

> Original: [https://www.geeksforgeeks.org/php-splfileinfo-getgroup-function/](https://www.geeksforgeeks.org/php-splfileinfo-getgroup-function/)

`SplFileInfo::getGroup()` 函数是 PHP 中标准 PHP 库 (SPL) 的内置函数，用于获取文件组。

## 语法

```php
int SplFileInfo::getGroup( void )
```

## 参数

此函数不接受任何参数。

## 返回值

此函数返回一个包含组 ID 的整数。

以下程序说明 PHP 中的 `SplFileInfo::getGroup()` 函数：

## 程序 1

```php
<?php
// PHP Program to illustrate
// Splfileinfo getGroup function

// Create new SPlFileInfo Object
$file = new SplFileInfo("gfg.txt");

// Print result
print_r($file->getGroup());

?>
```

## 程序 2

```php
<?php

// PHP program to use array to check multiple files

$GFG = array (
    "/home/rajvir/Desktop/GeeksforGeeks/dummy.php",
    "/home/rajvir/Desktop/gfg.txt",
    "/var/www/html/gfg.php",
    "demo.c"
);

foreach ($GFG as $file_name) {

// Create new SPlFileInfo Object
    $file = new SplFileInfo($file_name);

// Print result
    print_r($file->getGroup());

}
?>
```

**引用：**[http://php.net/manual/en/splfileinfo.getgroup.php](http://php.net/manual/en/splfileinfo.getgroup.php)