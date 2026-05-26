# PHP `strtr()` 函数：子字符串替换

> 原文：[https://www.geeksforgeeks.org/php-strtr-replacing-substrings/](https://www.geeksforgeeks.org/php-strtr-replacing-substrings/)

## 简介
`strtr()` 函数用于将一个字符串中的给定子字符串替换为另一个字符串。我们也可以通过传递一组键值对来执行多个替换。

例如：
```php
Input : $str = "Hmrrb GmmksfbrGmmks";
        $from = "rbm";
        $to = "loe";
Output : Hello GeeksforGeeks

Input : $str = "Hello world";
        $arr = array("Hello" => "I Love", "world" => "GeeksforGeeks");
Output : I Love GeeksforGeeks
```

## 语法
```php
string strtr ( string $string, string $from, string $to)

// 或者

string strtr (string $string, array $from_to_pairs)
```

## 参数
此函数接受两个或三个参数，所有参数都是必须传递的。

**语法 1 的参数：**
*   `$string`：表示给定的输入字符串。
*   `$from`：表示要翻译（替换）的子字符串。
*   `$to`：表示 `$from` 子串翻译（替换）后的子串。

**语法 2 的参数：**
*   `$string`：表示给定的输入字符串。
*   `$from_to_pairs`：表示一个包含各自 `from-to` 键值对的数组。

## 返回值
此函数返回一个字符串，其中 `$string` 中的子字符串（或字符）被 `$to` 子字符串（或 `$from_to_pairs` 数组中对应的值）替换。

请注意，如果 `$from` 和 `$to` 的长度不同，则替换行为取决于较短的长度。

## 示例
下面的程序说明了 PHP 中的 `strtr()` 函数：

**程序 1：**
```php
<?php

// 原始字符串
$str = "GzzksworGzzks is zverything.";

// from 和 to 项
$from = "zw";
$to = "ef";

// 调用 strtr() 函数
$resStr = strtr($str, $from, $to);

print_r($resStr);

?>
```
输出：
```php
GeeksforGeeks is everything.
```

**程序 2：**
```php
<?php

// 原始字符串
$str = "Hi there";

// 声明 from-to 对的数组
$arr = array("Hi" => "Be", "there" => "Happy");

// 调用 strtr() 函数
$resStr = strtr($str, $arr);

print_r($resStr);

?>
```
输出：
```php
Be Happy
```

## 参考资料
[http://php.net/manual/en/function.strtr.php](http://php.net/manual/en/function.strtr.php)