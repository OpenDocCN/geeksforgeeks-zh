# PHP | ArrayIterator::__construct() 函数

> 原文：[https://www.geeksforgeeks.org/php-arrayiterator-__construct-function/](https://www.geeksforgeeks.org/php-arrayiterator-__construct-function/)

**`ArrayIterator::__construct()` 函数**是 PHP 中的一个内置函数，用于构造一个数组迭代器。

## 语法

```php
public ArrayIterator::__construct( mixed $array, int $flags = 0 )
```

## 参数

这个函数接受两个参数，如下所述：

*   `$array`：此参数保存数组或对象迭代器数组。
*   `$flags`：此参数控制数组生成器对象的行为。

## 返回值

该函数返回 `ArrayIterator` 对象。

下面的程序说明了 PHP 中的 `ArrayIterator::__construct()` 函数：

## 程序 1

```php
<?php

// Declare an ArrayIterator
$arrItr = new ArrayIterator(
    array('G', 'e', 'e', 'k', 's', 'f', 'o', 'r'),
    ArrayIterator::ARRAY_AS_PROPS
);

// Display the elements
while($arrItr->valid()) {
    echo $arrItr->current();
    $arrItr->next();
}

?>
```

### 输出

```php
Geeksfor
```

## 程序 2

```php
<?php

// Declare an ArrayIterator
$arrItr = new ArrayIterator(
    array("Geeks", "for", "Geeks"), 
    ArrayIterator::STD_PROP_LIST
);

// Display the elements
foreach ($arrItr as $key => $val) {
    echo $key . " => " . $val . "\n";
}

?>
```

### 输出

```php
0 => Geeks
1 => for
2 => Geeks
```

## 参考

[https://www.php.net/manual/en/arrayiterator.construct.php](https://www.php.net/manual/en/arrayiterator.construct.php)