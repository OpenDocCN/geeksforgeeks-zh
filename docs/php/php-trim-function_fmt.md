# PHP `trim()` 函数

> 原文：[https://www.geeksforgeeks.org/php-trim-function/](https://www.geeksforgeeks.org/php-trim-function/)

PHP 中的 `trim()` 函数是一个内置函数，可以删除字符串左右两边的空格和预定义字符。

## 相关函数

*   [PHP | ltrim() 函数](https://www.geeksforgeeks.org/php-ltrim-function/)
*   [PHP | rtrim() 函数](https://www.geeksforgeeks.org/php-rtrim-function/)

## 语法

```php
trim($string, $charlist)
```

## 参数

此函数接受一个必选参数和一个可选参数，如以上语法所示，如下所述。

1.  `$string`：此参数指定要从中删除空格和左右预定义字符的字符串。
2.  `$charlist`：这是一个可选参数，指定要从字符串中删除的字符。如果未提及，则删除以下所有字符：
    *   `" "`（空格）
    *   `"\t"`（制表符）
    *   `"\n"`（换行符）
    *   `"\x0B"`（垂直制表符）
    *   `"\r"`（回车符）

## 返回值

它通过删除字符串左右两侧的空格以及预定义字符来返回修改后的字符串。

## 示例程序

以下程序说明了 `trim()` 函数：

### 程序 1

```php
<?php
// PHP program to demonstrate the use of trim() 
// function when second parameter is present

// removes the predefined characters from 
// front and back 
$str = "Hello World!";
echo trim($str, "Hell!");
?>
```

### 程序 2

```php
<?php
// PHP program to demonstrate the use of trim() 
// function when second parameter is absent

$str = "  geeks for geeks ";

// removes all leading and trailing whitespaces 
echo trim($str);
?>
```

## 引用

[http://php.net/manual/en/function.trim.php](http://php.net/manual/en/function.trim.php)