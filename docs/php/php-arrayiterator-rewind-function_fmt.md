# ArrayIterator::rewind() 函数

> 原文: [https://www.geeksforgeeks.org/php-arrayiterator-rewind-function/](https://www.geeksforgeeks.org/php-arrayiterator-rewind-function/)

`ArrayIterator::rewind()` 函数是 PHP 中的一个内置函数，用于将数组倒回起点。

## 语法

```php
void ArrayIterator::rewind( void )
```

## 参数

此函数不接受任何参数。

## 返回值

该函数不返回值。

## 程序示例

下面的程序说明了 PHP 中的 `ArrayIterator::rewind()` 函数：

### 程序 1

```php
<?php

// Declare an ArrayIterator
$arrItr = new ArrayIterator(
    array(
        "a" => 4,
        "b" => 2,
        "g" => 8,
        "d" => 6,
        "e" => 1,
        "f" => 9
    )
);

// Move to last position
$arrItr->seek(5);

// Display the next value
var_dump($arrItr->next());

// Move to start position
$arrItr->rewind();

// Display the current element
echo $arrItr->current();

?>
```

**输出:**

```php
NULL
```

### 程序 2

```php
<?php

// Declare an ArrayIterator
$arrItr = new ArrayIterator(
    array(
        "b" => "for",
        "a" => "Geeks",
        "e" => "Science",
        "c" => "Geeks",
        "f" => "Portal",
        "d" => "Computer"
    )
);

// Check the validity of ArrayIterator
while($arrItr->valid()) {
    $arrItr->next();
}

// Move to start position
$arrItr->rewind();

// Display the current element
echo $arrItr->current();

?>
```

**输出:**

```php
for
```

## 参考

[https://www.php.net/manual/en/arrayiterator.rewind.php](https://www.php.net/manual/en/arrayiterator.rewind.php)