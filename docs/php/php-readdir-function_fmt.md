# PHP readdir() 函数

> Original: [https://www.geeksforgeeks.org/php-readdir-function/](https://www.geeksforgeeks.org/php-readdir-function/)

PHP 中的 `readdir()` 函数是一个内置函数，用于返回目录中下一个条目的名称。该方法按文件名存储在文件名系统中的顺序返回文件名。

目录句柄作为参数发送给 `readdir()` 函数，如果成功则返回条目名称/文件名，如果失败则返回 `False`。

**语法：**

```php
readdir(dir_handle)
```

**使用的参数：** PHP 中的 `readdir()` 函数接受一个参数。

*   `DIR_HANDLE`：这是一个强制参数，指定之前由 `opendir()` 函数打开的句柄资源。

**返回值：** 成功时返回条目名/文件名，失败时返回 `False`。

**错误和异常：**

1.  如果用户未指定目录句柄参数，`readdir()` 函数会假定使用最后由 `opendir()` 打开的链接。
2.  除了返回布尔值 `FALSE` 外，`readdir()` 函数有时也可能返回一个计算结果为 `FALSE` 的非布尔值。

以下程序说明了 `readdir()` 函数：

**程序 1：**

```php
<?php

// opening a directory
$dir_handle = opendir("user/gfg/");

// reading the contents of the directory
while(($file_name = readdir($dir_handle)) !== false) 
{ 
echo("File Name: " . $file_name);
echo "<br>" ; 
}

// closing the directory
closedir($dir_handle);
?>
```

**程序 2：**

```php
<?php

// opening a directory
$dir_handle = opendir("user/gfg/");

if(is_resource($dir_handle)) 
{

// reading the contents of the directory
while(($file_name = readdir($dir_handle)) !== false) 
{ 
echo("File Name: " . $file_name);
echo "<br>" ; 
}

// closing the directory
closedir($dir_handle); 
} 
else
{
echo("Failed to Open.");
} 
?>
```

**引用：** [http://php.net/manual/en/function.readdir.php](http://php.net/manual/en/function.readdir.php)