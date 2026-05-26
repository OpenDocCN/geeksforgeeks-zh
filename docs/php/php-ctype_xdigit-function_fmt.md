# PHP `ctype_xdigit()` 函数

> 原文：[https://www.geeksforgeeks.org/php-ctype_xdigit-function/](https://www.geeksforgeeks.org/php-ctype_xdigit-function/)

PHP 中的 `ctype_xdigit()` 函数用于检查字符串/文本的每个字符是否为十六进制数字。如果所有字符都是十六进制，则返回 `TRUE`，否则返回 `FALSE`。

## 语法

```php
ctype_xdigit(string $text): bool
```

## 参数

*   `text`：必选参数，指定要测试的字符串。

## 返回值

如果字符串的所有字符都是十六进制数字，则返回 `TRUE`，否则返回 `FALSE`。

## 示例

```
输入:  ABCDEF0123
输出:  Yes

输入: GFG2018
输出: No
```

> 注意：它检查的是十进制数字或来自 `[A-F, a-f]` 的字符。

下面的程序说明了 `ctype_xdigit()` 函数的使用。

### 程序 1

```php
<?php
// PHP program to check given string is 
// Hexadecimal character or not

$string = 'ABab012';

// Checking above string by using
// of ctype_xdigit() function.
if ( ctype_xdigit($string)) {

// if true then return Yes
    echo "Yes \n";

} else {

// if False then return No
    echo "No \n";
}
?>
```

**输出：**

```
Yes
```

### 程序 2

再举一个 `ctype_xdigit()` 函数的例子，通过将输入作为字符串数组，检查当输入包含大写、小写和符号字符时，它是如何工作的。

```php
<?php
// PHP program to check given string is 
//Hexadecimal character or not

$strings = array(
    'ABCDEF',
    'abcdef',
    '0123456789X',
    '0123456789',
    'Gg@(*&)',
    'GFG'
);

// Checking above given strings 
//by used of ctype_xdigit() function .
foreach ($strings as $test) {

if (ctype_xdigit($test)) {
         echo "Yes \n";
    } else {
         echo "No \n";
    }
}

?>
```

**输出：**

```
Yes
Yes
No
Yes
No
No
```

## 引用

[http://php.net/manual/en/function.ctype-xdigit.php](http://php.net/manual/en/function.ctype-xdigit.php)