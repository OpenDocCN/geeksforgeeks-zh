# PHP Ds\Sequence::find() 函数

> 原文：[https://www.geeksforgeeks.org/php-dssequence-find-function/](https://www.geeksforgeeks.org/php-dssequence-find-function/)

## 函数描述

`Ds\Sequence::find()` 函数是 PHP 中的一个内置函数，用于从序列中查找值。如果序列中存在该值，则返回其索引值，否则返回 `false`。

## 语法

```php
abstract public Ds\Sequence::find ( mixed $value ) : mixed
```

## 参数

此函数接受单个参数 `$value`，该参数用于检查其是否出现在序列中。

## 返回值

此函数成功时返回值的索引，失败时返回 `false`。

## 示例程序

以下程序说明了 PHP 中的 `Ds\Sequence::find()` 函数：

### 程序 1

```php
<?php

// 创建新序列
$seq = new \Ds\Vector([21, 23, "p", "x"]);

// 使用 find() 函数
var_dump($seq->find("G"));

// 使用 find() 函数
var_dump($seq->find(21));

// 使用 find() 函数
var_dump($seq->find(10));

// 使用 find() 函数
var_dump($seq->find("x"));

// 使用 find() 函数
var_dump($seq->find("p"));

?>
```

### 程序 2

```php
<?php

// 创建新序列
$seq = new \Ds\Vector(["G", "E", "E",
        "K", "S", "1", "2", 1, 2, 3, 4]);

// 使用 find() 函数
var_dump($seq->find("G"));

// 使用 find() 函数
var_dump($seq->find(1));

// 使用 find() 函数
var_dump($seq->find(10));

// 使用 find() 函数
var_dump($seq->find("1"));

// 使用 find() 函数
var_dump($seq->find("k"));

// 使用 find() 函数
var_dump($seq->find("F"));

// 使用 find() 函数
var_dump($seq->find("4"));

?>
```

## 引用

[http://php.net/manual/en/ds-sequence.find.php](http://php.net/manual/en/ds-sequence.find.php)