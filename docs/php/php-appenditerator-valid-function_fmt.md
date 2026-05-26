# PHP | AppendIterator::valid() 函数

> 原文: [https://www.geeksforgeeks.org/php-appenditerator-valid-function/](https://www.geeksforgeeks.org/php-appenditerator-valid-function/)

`AppendIterator::valid()` 函数是 PHP 中的一个内置函数，用于检查当前元素的有效性。

**语法:**

```php
bool AppendIterator::valid( void )
```

**参数:** 此函数不接受任何参数。

**返回值:** 如果当前迭代有效，该函数返回 `true`，否则返回 `false`。

下面的程序说明了 PHP 中的 `AppendIterator::valid()` 函数:

**程序 1:**

```php
<?php

// Declare an ArrayIterator
$arr = new ArrayIterator(array('G', 'e', 'e', 'k', 's'));

// Create a new AppendIterator
$itr = new AppendIterator;
$itr->append($arr);

// Check the validity and display
// the result
while($itr->valid()) {
    echo $itr->current();
    $itr->next();
}

?>
```

**输出:**

```php
Geeks
```

**程序 2:**

```php
<?php

// Declare an ArrayIterator
$arr1 = new ArrayIterator(array("Geeks", "for", "Geeks"));
$arr2 = new ArrayIterator(array("Computer", "Science", "Portal"));

// Create a new AppendIterator
$itr = new AppendIterator;
$itr->append($arr1);
$itr->append($arr2);

// Using rewind function
$itr->rewind();

// Check the validity and display the result
while($itr->valid()) {
    var_dump($itr->current());

    // Moving to next element
    $itr->next();
}

?>
```

**输出:**

```php
string(5) "Geeks"
string(3) "for"
string(5) "Geeks"
string(8) "Computer"
string(7) "Science"
string(6) "Portal"
```

**参考:** [https://www.php.net/manual/en/appenditerator.valid.php](https://www.php.net/manual/en/appenditerator.valid.php)