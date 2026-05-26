# PHP str_word_count() 函数

> Original: [https://www.geeksforgeeks.org/php-str_word_count-function/](https://www.geeksforgeeks.org/php-str_word_count-function/)

`str_word_count()` 函数是 PHP 中的内置函数，用于返回有关字符串中使用的单词的信息，如字符串中的单词总数、单词在字符串中的位置等。

## 语法

```php
str_word_count ( $string , $returnVal, $chars )
```

## 参数说明

### `$string`
此参数指定用户要计算其单词的字符串。这不是可选参数。

### `$returnVal`
`str_word_count()` 函数的返回值由 `$returnVal` 参数指定。可选参数，默认值为 0。
该参数可以根据需要采用以下值：
*   `0`：它返回字符串 `$string` 中的字数。
*   `1`：它返回一个数组，其中包含在字符串中找到的所有单词。
*   `2`：它返回一个具有键-值对的关联数组，其中键定义单词在字符串中的位置，值是单词本身。

### `$chars`
这是一个可选参数，用于指定应视为‘word’的附加字符列表。

## 返回类型
函数的返回类型取决于参数 `$returnVal`，返回值如上所述。

## 示例

以下程序解释了 `str_word_count()` 函数的工作原理：

### 1. 计算字符串中的单词数
要仅显示字符串中的单词数，应按以下方式执行 `str_word_count()` 函数：

```php
<?php
$mystring = "Twinkle twinkl4e little star";
print_r(str_word_count($mystring));
?>
```

### 2. 查找字符串中的单词
要返回一个包含字符串中单词的数组，应按以下方式执行 `str_word_count()` 函数：

```php
<?php
$mystring = "Twinkle twinkl4e little star";
print_r(str_word_count($mystring, 1));
?>
```

输出：
```
Array ( [0] => Twinkle [1] => twinkl [2] => e [3] => little [4] => star )
```

### 3. 查找字符串中的单词及其数字位置
要返回一个包含字符串中单词及其数字位置的数组，应按以下方式执行 `str_word_count()` 函数：

```php
<?php
$mystring = "Twinkle twinkl4e little star";
print_r(str_word_count($mystring, 2));
?>
```

输出：
```
Array ( [0] => Twinkle [8] => twinkl [15] => e [17] => little [24] => star )
```

### 4. 将特殊字符视为单词一部分时查找单词
要返回一个包含字符串中单词的数组，其中某个字符应被视为单词的一部分，应按以下方式执行 `str_word_count()` 函数：

```php
<?php
$mystring = "Twinkle twinkl4e little star";
print_r(str_word_count($mystring, 2 ,4));
?>
```

输出：
```
Array ( [0] => Twinkle [8] => twinkl4e [17] => little [24] => star )
```