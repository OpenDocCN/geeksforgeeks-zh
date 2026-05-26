# PHP | array_chunk()函数

> 原文: [https://www.geeksforgeeks.org/php-array_chunk-function/](https://www.geeksforgeeks.org/php-array_chunk-function/)

`array_chunk()`函数是 PHP 中的一个内置函数，用于根据传递给函数的参数将数组拆分成给定大小的部分或块。最后一个块包含的元素可能少于所需的块大小。

## 语法

```php
array array_chunk( $array, $size, $preserve_keys )
```

## 参数

该函数接受三个参数，如上语法所示。参数描述如下:

*   `$array`: 此参数指示要分区的数组。
*   `$size`: 此参数是一个整数，定义要创建的块的大小。
*   `$preserve_keys`: 此参数接受布尔值。当此参数设置为 `true` 时，键被保留，否则块从 0 开始重新索引。

## 返回值

该函数返回从 0 开始索引的多维数组。每个块包含 `$size` 数量的元素，除了最后一个块可能包含较少数量的元素。

## 示例

```php
Input : $input_array = array('a', 'b', 'c', 'd', 'e');
        array_chunk($input_array, 2);
Output : Array(
                [0] => Array
                (
                    [0] => a
                    [1] => b
                )
                [1] => Array
                (
                    [0] => c
                    [1] => d
                )
                [2] => Array
                (
                    [0] => e
                )
            )

Input : $input_array = array('a', 'b', 'c', 'd', 'e');
       array_chunk($input_array, 2, true)
Output :    Array
            (
                [0] => Array
                (
                    [0] => a
                    [1] => b
                )
                [1] => Array
                (
                    [2] => c
                    [3] => d
                )
                [2] => Array
                (
                    [4] => e
                )
            )
```

在第一个例子中，返回了一个多维数组，其中每个块包含 `2` 个元素。在第二个示例中，由于第三个参数作为 `true` 传递，因此每个块中元素的索引与创建该块的原始数组中元素的索引相同。在这种情况下，每个块包含 `2` 个元素，它们是传递给函数的大小值。

下面的程序说明了 PHP 中的 `array_chunk()`函数:

### 程序 1

```php
<?php

$input_array = array('a', 'b', 'c', 'd', 'e');

print_r(array_chunk($input_array, 2));

?>
```

**输出:**

```php
Array
(
    [0] => Array
        (
            [0] => a
            [1] => b
        )
    [1] => Array
        (
            [0] => c
            [1] => d
        )
    [2] => Array
        (
            [0] => e
        )
)
```

### 程序 2

```php
<?php

$input_array = array('a', 'b', 'c', 'd', 'e');

print_r(array_chunk($input_array, 2, true));

?>
```

**输出:**

```php
Array
(
    [0] => Array
        (
            [0] => a
            [1] => b
        )
    [1] => Array
        (
            [2] => c
            [3] => d
        )
    [2] => Array
        (
            [4] => e
        )
)
```

## 参考

`http://php.net/manual/en/function.array-chunk.php`