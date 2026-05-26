# PHP str_starts_with()函数

> Original: [https://www.geeksforgeeks.org/php-str_starts_with-function/](https://www.geeksforgeeks.org/php-str_starts_with-function/)

这是 PHP 8 中的一个预定义函数，用于对给定字符串执行区分大小写的搜索。`str_starts_with()`通常检查字符串是否以子字符串开头。如果字符串以子字符串开头，则`str_starts_with()`将返回`true`，否则将返回`false`。

## 语法

```php
str_starts_with($string, $substring) 
```

## 参数

*   `$string`: 此参数指代需要检查起始字符串的字符串。
*   `$substring`: 此参数代表需要检查的字符串。

## 返回类型

如果字符串以子字符串开头，则`str_starts_with()`将返回`true`，否则将返回`false`。

## 主要特点

*   `str_starts_with()`本质上是区分大小写的。
*   `str_starts_with()`总是返回布尔值。
*   `str_starts_with()`可用于检查字符的开头或字符串的开头。
*   低于 8 的 PHP 版本不支持`STR_STARTS_WITH()`。

## 示例 1

在下面的程序中，我们创建了三个变量`$name`来存储类型字符串的名称，`$beginsWith`来存储需要用`$name`检查的子字符串，和`$result`来存储根据`str_starts_with()`计算的表达式的结果。如果字符串`$name`以子字符串`$beginsWith`开头，则`str_starts_with()`将返回`TRUE`，否则将返回`FALSE`，并相应地为`$result`赋值。

```php
<?php

$name = 'Saurabh Singh';
    $beginsWith = 'S';

$result = str_starts_with($name, $beginsWith) ? 'is' : 'is not';

echo "The string \"$name\" $result starting with $beginsWith";

?>
```

**输出：**

```php
The string "Saurabh Singh" is starting with S
```

## 示例 2

在第一个示例中，我们取句子的开头字符进行搜索。在本例中，我们采用了句子开头的完整单词，它还将在 if 条件中返回`TRUE`，并进一步相应地执行条件部分。

```php
<?php

$sentance = 'The Big Brown Fox';
    $beginsWith = 'The';

if(str_starts_with($sentance , $beginsWith) )
    {
      echo "The string \"$sentance\" begins with \"$beginsWith\" ";
    }
    else
    {
      echo "The string \"$sentance\" does not begins with \"$beginsWith\" ";
    }

?>
```

**输出：**

```php
The string "The Big Brown Fox" begins with "The" 
```

**引用：** [https://www.php.net/manual/en/function.str-starts-with.php](https://www.php.net/manual/en/function.str-starts-with.php)