# PHP | ArrayIterator serialize()函数

> 原文: [https://www.geeksforgeeks.org/php-arrayiterator-serialize-function/](https://www.geeksforgeeks.org/php-arrayiterator-serialize-function/)

## ArrayIterator::serialize()函数

`ArrayIterator::serialize()`函数是 PHP 中的一个内置函数，用于序列化数组迭代器。

### 语法

```php
string ArrayIterator::serialize( void )
```

### 参数

此函数不接受任何参数。

### 返回值

该函数返回序列化数组运算符。

下面的程序说明了 PHP 中的 `ArrayIterator::serialize()`函数:

### 程序 1

```php
<?php

// Declare an ArrayIterator
$arrItr = new ArrayIterator(
    array('G', 'e', 'e', 'k', 's')
);

// Serialize the element
$serialize = $arrItr->serialize();

// Display the output
var_dump($serialize);

?>
```

### 输出

> string(81) "x:i:0;a:5:{i:0;s:1:"G";i:1;s:1:"e";i:2;s:1:"e";i:3;s:1:"k";i:4;s:1:"s";}m:a:0:{}"

### 程序 2

```php
<?php

// Declare an ArrayIterator
$arrItr = new ArrayIterator(
    array(
        "a" => "Geeks",
        "b" => "for",
        "c" => "Geeks"
    )
);

// Append some elements
$arrItr->append("Computer");
$arrItr->append("Science");
$arrItr->append("Portal");

// Serialize the element
$serialize = $arrItr->serialize();

// Display the output
var_dump($serialize);

?>
```

### 输出

> string(133) "x:i:0;a:6:{s:1:"a";s:5:"Geeks";s:1:"b";s:3:"for";s:1:"c";s:5:"Geeks";i:0;s:8:"Computer";i:1;s:7:"Science";i:2;s:6:"Portal";}m:a:0:{}"

### 参考

[https://www.php.net/manual/en/arrayiterator.serialize.php](https://www.php.net/manual/en/arrayiterator.serialize.php)