# PHP CachingIterator::__construct() 函数

> 原文：[https://www.geeksforgeeks.org/php-cachingiterator-__construct-function/](https://www.geeksforgeeks.org/php-cachingiterator-__construct-function/)

`CachingIterator::__construct()` 函数是 PHP 中的一个内置函数，用于为迭代器构造一个新的 `CachingIterator` 对象。

## 语法

```php
public CachingIterator::__construct( Iterator $iterator, int $flags = self::CALL_TOSTRING )
```

## 参数

这个函数接受两个参数，如下所述：

*   `$iterator`：此参数保存被缓存的迭代器。
*   `$flags`：此参数存储标志的位掩码。

## 返回值

该函数不返回值。

## 示例

下面的程序说明了 PHP 中的 `CachingIterator::__construct()` 函数：

### 程序 1

```php
<?php

// Declare an array
$arr = array('G', 'e', 'e', 'k', 's');

// Create a new CachingIterator
$cachIt = new CachingIterator(
    new ArrayIterator($arr), 
    CachingIterator::FULL_CACHE
);

// Display the result
foreach($cachIt as $element) {
    echo $element . " ";
}

?>
```

**输出：**

```
G e e k s
```

### 程序 2

```php
<?php

// Declare an ArrayIterator
$arr = array(
    "a" => "Geeks",
    "b" => "for",
    "c" => "Geeks",
    "d" => "Computer",
    "e" => "Science",
    "f" => "Portal"
);

// Create a new CachingIterator
$cachIt = new CachingIterator(
    new ArrayIterator($arr), 
    CachingIterator::FULL_CACHE
);

// Display the result
foreach($cachIt as $key => $value) {
    echo $key . " => " . $value . "\n";
}

?>
```

**输出：**

```
a => Geeks
b => for
c => Geeks
d => Computer
e => Science
f => Portal
```

## 参考

[https://www.php.net/manual/en/cachingiterator.construct.php](https://www.php.net/manual/en/cachingiterator.construct.php)