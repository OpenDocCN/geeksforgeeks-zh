# 在 PHP 中将一个目录的全部内容复制到另一个目录

> 原文：[https://www.geeksforgeeks.org/copy-the-entire-contents-of-a-directory-to-another-directory-in-php/](https://www.geeksforgeeks.org/copy-the-entire-contents-of-a-directory-to-another-directory-in-php/)

给定一个目录，任务是使用 PHP 函数将目录的内容复制到另一个目录。有许多功能用于将一个目录的内容复制到另一个目录。

## 使用的功能

### `copy()` 函数
`copy()` 函数用于制作指定文件的副本。它将源文件复制到目标文件，如果目标文件已存在，则会被覆盖。`copy()` 函数成功时返回 `true`，失败时返回 `false`。

**语法：**
```php
bool copy($source, $dest)
```

### `opendir()` 函数
`opendir()` 函数用于打开一个目录句柄。要打开的目录路径作为参数发送给 `opendir()` 函数，成功时返回一个目录句柄资源，失败时返回 `FALSE`。

**语法：**
```php
opendir($path, $context)
```

### `is_dir()` 函数
`is_dir()` 函数用于检查指定的文件是否是一个目录。文件名作为参数发送给 `is_dir()` 函数，如果文件是目录则返回 `True`，否则返回 `False`。

**语法：**
```php
is_dir($file)
```

### `scandir()` 函数
`scandir()` 函数用于返回指定目录的文件和目录数组。`scandir()` 函数列出指定路径中存在的文件和目录。目录、流行为和文件/目录的排序顺序作为参数传递给 `scandir()` 函数，成功时返回文件名数组，失败时返回 `False`。

**语法：**
```php
scandir(directory, sorting_order, context)
```

### `readdir()` 函数
`readdir()` 函数用于返回目录中的下一个条目名称。此方法按文件系统中存储的顺序返回文件名。目录句柄作为参数发送给 `readdir()` 函数，成功时返回条目名称/文件名，失败时返回 `False`。

**语法：**
```php
readdir(dir_handle)
```

## 示例 1
本示例使用 `readdir()` 函数从源目录读取文件。

```php
<?php

function custom_copy($src, $dst) {

// open the source directory
    $dir = opendir($src);

// Make the destination directory if not exist
    @mkdir($dst);

// Loop through the files in source directory
    while( $file = readdir($dir) ) {

if (( $file != '.' ) && ( $file != '..' )) { 
            if ( is_dir($src . '/' . $file) ) 
            {

// Recursively calling custom copy function
                // for sub directory 
                custom_copy($src . '/' . $file, $dst . '/' . $file);

} 
            else { 
                copy($src . '/' . $file, $dst . '/' . $file); 
            } 
        } 
    }

closedir($dir);
}

$src = "C:/xampp/htdocs/geeks";

$dst = "C:/xampp/htdocs/gfg";

custom_copy($src, $dst);

?>
```

**输出：**

*   **在本地主机上运行程序前：**
    ![](img/23d251b3649e70c6586e2ca34801a5ae.png)
*   **在本地主机上运行程序后：**
    ![](img/96499cf62953d2da505d695453f3e254.png)

## 示例 2
本示例使用 `scandir()` 函数从源目录读取文件。

```php
<?php

function custom_copy($src, $dst) {

// open the source directory
    $dir = opendir($src);

// Make the destination directory if not exist
    @mkdir($dst);

// Loop through the files in source directory
    foreach (scandir($src) as $file) {

if (( $file != '.' ) && ( $file != '..' )) { 
            if ( is_dir($src . '/' . $file) ) 
            {

// Recursively calling custom copy function
                // for sub directory 
                custom_copy($src . '/' . $file, $dst . '/' . $file);

} 
            else { 
                copy($src . '/' . $file, $dst . '/' . $file); 
            } 
        } 
    }

closedir($dir);
}

$src = "C:/xampp/htdocs/geeks";

$dst = "C:/xampp/htdocs/gfg";

custom_copy($src, $dst);

?>
```

**输出：**

*   **在本地主机上运行程序前：**
    ![](img/23d251b3649e70c6586e2ca34801a5ae.png)
*   **在本地主机上运行程序后：**
    ![](img/96499cf62953d2da505d695453f3e254.png)