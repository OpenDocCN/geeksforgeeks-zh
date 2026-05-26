# PHP `count_chars()` 函数

> Original: [https://www.geeksforgeeks.org/php-count_chars-function/](https://www.geeksforgeeks.org/php-count_chars-function/)

`count_chars()` 是 PHP 中的一个内置函数，用于执行几个与字符串相关的操作，如字符串中出现的 ASCII 字符数。

## 语法

```php
count_chars(string, return_mode);
```

## 参数

`count_chars()` 函数接受两个参数 `string` 和 `return_mode`，如下所示：

*   `string`: 此参数指代您想要执行操作的输入字符串。
*   `return_mode`: 此参数可选。它定义了需要在字符串上执行的操作。接受值 0、1、2、3、4。
    1.  `0`: 如果选择此模式，函数将返回一个键值对数组，其中键是 ASCII 值，对应的值是该 ASCII 值出现的次数。
    2.  `1`: 如果选择此模式，`count_chars()` 函数将返回一个键值对数组，其中键是 ASCII 值，对应的值是该 ASCII 值出现的次数。此处，数组将仅包含频率大于 0 的 ASCII 值形式的键。
    3.  `2`: 在此模式下，函数返回一个键值对数组，其中键是字符串中频率为 0 的 ASCII 值。
    4.  `3`: 在此模式下，`count_chars()` 函数按升序返回字符串中使用的所有不同字符组成的字符串。
    5.  `4`: 在此模式下，`count_chars()` 函数返回输入字符串中未使用的字符串。

## 返回类型

此函数将返回一个数组或字符串，具体取决于上述的 `return_mode` 参数。

## 示例

```php
Input : string = "GeeksforGeeks"  ,  return_mode = 3
Output : Gefkors
```

下面是说明 `count_chars()` 函数工作原理的 PHP 程序：

```php
<?php
    // PHP program to illustrate count_chars()

    // Input string
    $string = "geeksforgeeks";

    // return_mode 1
    print_r(count_chars($string, 1));

    // return_mode 3
    print_r(count_chars($string, 3));

    // return_mode 4
    print_r(count_chars($string, 4));
?>
```

上面的程序显示了字符串“geeksforgeek”的返回值，其中 `return_mode` 为 1、3 和 4。您可以通过更改函数调用中的 `return_mode` 的值来修改程序，以查看模式 0 和 2 的返回值。