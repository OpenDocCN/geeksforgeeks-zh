# ArrayIterator::offsetSet 函数

> 原文：[https://www.geeksforgeeks.org/php-arrayiterator-offsetset-function/](https://www.geeksforgeeks.org/php-arrayiterator-offsetset-function/)

`ArrayIterator::offsetSet()` 函数是 PHP 中的一个内置函数，用于设置偏移量的值。

## 语法

```php
void ArrayIterator::offsetSet( mixed $index, mixed $newval )
```

## 参数

该函数接受两个参数：

*   `$index`：此参数存储要设置的偏移量的索引。
*   `$newval`：此参数保存要存储在给定索引处的新值。

## 返回值

该函数不返回值。

## 示例

下面的程序说明了 PHP 中的 `ArrayIterator::offsetSet()` 函数：

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

// Update the value at index 1 
$arrItr->offsetSet("g", "Geeks");

// Print the updated ArrayObject 
print_r($arrItr);

?>
```

**输出：**

```php
ArrayIterator Object
(
    [storage:ArrayIterator:private] => Array
        (
            [a] => 4
            [b] => 2
            [g] => Geeks
            [d] => 6
            [e] => 1
            [f] => 9
        )

)
```

### 程序 2

```php
<?php

// Declare an ArrayIterator
$arrItr = new ArrayIterator(
    array(
        "for", "Geeks", "Science",
        "Geeks", "Portal", "Computer"
    )
);

// Update the value at index 1 
$arrItr->offsetSet(1, "GeeksforGeeks");

// Print the updated ArrayObject 
print_r($arrItr);

?>
```

**输出：**

```php
ArrayIterator Object
(
    [storage:ArrayIterator:private] => Array
        (
            [0] => for
            [1] => GeeksforGeeks
            [2] => Science
            [3] => Geeks
            [4] => Portal
            [5] => Computer
        )

)
```

## 参考

[https://www.php.net/manual/en/arrayiterator.offsetset.php](https://www.php.net/manual/en/arrayiterator.offsetset.php)