# PHP `gmp_import()` 函数

> Original: [https://www.geeksforgeeks.org/php-gmp_import-function/](https://www.geeksforgeeks.org/php-gmp_import-function/)

`gmp_import()` 函数是 PHP 中的一个内置函数，用于从二进制字符串导入 GMP 编号（[GNU Multiple Precision](https://en.wikipedia.org/wiki/GNU_Multiple_Precision_Arithmetic_Library)：表示大数）。

## 语法

```php
GMP gmp_import ( string $data, int $word_size, int $options )
```

## 参数

`gmp_import()` 函数接受上述三个参数，如下所述：

*   `$data`：它是必选参数之一，包含应该导入的二进制字符串。
*   `$word_size`：这也是 `gmp_import()` 函数的参数。它包含每个二进制数据块中的字节数。该参数主要与 `$options` 参数同时使用。此参数的默认值为 1。
*   `$options`：此参数的默认值为 `GMP_MSW_FIRST|GMP_Native_Endian`。

## 返回值

函数成功时返回 GMP 编号，失败时返回 `false`。

## 示例

### 程序 1

以下程序说明 PHP 中的 `gmp_import()` 函数：

```php
<?php
// php code implementing gmp_import() function

$number = gmp_import("\0");

// The gmp_strval() returns the string value of the gmp number
echo gmp_strval($number) . "\n";

?>
```

### 程序 2

```php
<?php
// php code implementing the gmp_import() function

$number = gmp_import("\0\1\2");

// The strval() returns the string value of the gmp number
echo gmp_strval($number) . "\n";

?>
```

## 相关文章

*   [PHP|gmp_com()函数](https://www.geeksforgeeks.org/php-gmp_com-function/)
*   [PHP|gmp_and()函数](https://www.geeksforgeeks.org/php-gmp_and-function/)
*   [PHP|GMP 档案](https://www.geeksforgeeks.org/tag/php-gmp/)

## 参考

[php.net/Manual/en/function.gmp-import.php](http://php.net/manual/en/function.gmp-import.php)