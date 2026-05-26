# PHP Ds\Deque::set() 函数

> Original: [https://www.geeksforgeeks.org/php-dsdeque-set-function/](https://www.geeksforgeeks.org/php-dsdeque-set-function/)

`Ds\Deque::set()` 函数是 PHP 中的一个内置函数，用于设置 Deque 中给定索引处的值。

## 语法

```php
public Ds\Deque::set( $index, $value ) : void
```

## 参数

此函数接受两个参数：

*   `$index`: 此参数保存要设置元素的索引值。
*   `$value`: 此参数保存要在给定索引处设置的值。

## 返回值

此函数不返回任何值。

## 示例

以下程序说明了 PHP 中的 `Ds\Deque::set()` 函数：

### 程序 1

```php
<?php

// Declare a deque
$deck = new \Ds\Deque(["geeks", "for", "geeks", "practice"]);

echo("Elements of Deque\n");

// Display the Deque elements
print_r($deck);

// Updating the deque element at index 2
$deck->set(2, "geeksforgeeks");

echo("Deque after setting value at index 2\n");

// Display the Deque elements
print_r($deck);

?>
```

**输出：**

```
Elements of Deque
Ds\Deque Object
(
    [0] => geeks
    [1] => for
    [2] => geeks
    [3] => practice
)
Deque after setting value at index 2
Ds\Deque Object
(
    [0] => geeks
    [1] => for
    [2] => geeksforgeeks
    [3] => practice
)
```

### 程序 2

```php
<?php

// Declare a deque
$deck = new \Ds\Deque([1, 2, 3, 4, 5, 6]);

echo("Elements of Deque\n");

// Display the Deque elements
print_r($deck);

// Updating the deque element at index 2
$deck->set(4, 10);

echo("Deque after setting value at index 2\n");

// Display the Deque elements
print_r($deck);

?>
```

**输出：**

```
Elements of Deque
Ds\Deque Object
(
    [0] => 1
    [1] => 2
    [2] => 3
    [3] => 4
    [4] => 5
    [5] => 6
)
Deque after setting value at index 2
Ds\Deque Object
(
    [0] => 1
    [1] => 2
    [2] => 3
    [3] => 4
    [4] => 10
    [5] => 6
)
```

## 引用

[http://php.net/manual/en/ds-deque.set.php](http://php.net/manual/en/ds-deque.set.php)