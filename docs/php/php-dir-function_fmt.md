# PHP dir()函数

> Original: [https://www.geeksforgeeks.org/php-dir-function/](https://www.geeksforgeeks.org/php-dir-function/)

## 描述

PHP 中的 `dir()` 函数是一个内置函数，用于返回 `Directory` 类的实例。函数的作用是：读取一个目录，它包括以下内容：

1.  打开给定的目录。
2.  `dir()` 的两个属性 `Handle` 和 `Path` 可用。
3.  `Handle` 和 `Path` 属性都有三个方法：`Read()`、`Rewind()` 和 `Close()`。

目录的路径作为参数发送给 `opendir()` 函数，如果成功则返回 `Directory` 类的实例，如果失败则返回 `False`。

## 语法

```php
dir($directory, $context)
```

## 参数

`dir()` 函数接受两个参数，如下所述。

*   `$DIRECTORY`：这是一个强制参数，用于指定目录路径。
*   `$CONTEXT`：这是一个可选参数，用于指定流的行为。

## 返回值

成功时返回 `Directory` 类的实例，失败时返回 `False`。

## 错误和异常

1.  如果向 `dir()` 传递错误的参数，则返回 `null` 值。
2.  `Read` 方法返回目录条目的顺序取决于系统。

## 示例

以下程序说明了 `dir()` 函数：

### 程序 1

```php
<?php

$dir_handle = dir("user/gfg");

while(($file_name = $dirhandle->read()) !== false) 
{ 
    echo("File Name : " . $file_name);
    echo "<br>" ; 
}

?>
```

发帖主题：Re：Колибри0.7.8.0

### 程序 2

```php
<?php

$dir_handle = dir("user/gfg");

echo("Directory Path: " . $dir_handle->path . "<br>");

echo("Directory Handler ID: " . $dir_handle->handle . "<br>");

while(($file_name = $dir_handle->read()) !== false) 
{ 
   echo("File Name: " . $file_name);
   echo "<br>" ; 
}

$dir_handle->close();

?>
```

发帖主题：Re：Колибри0.7.8.0

## 引用

[http://php.net/manual/en/function.dir.php](http://php.net/manual/en/function.dir.php)