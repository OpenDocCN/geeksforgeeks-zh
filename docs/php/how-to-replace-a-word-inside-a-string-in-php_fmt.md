# 如何在 PHP 中替换字符串内部的一个单词？

> 原文: [https://www.geeksforgeeks.org/how-to-replace-a-word-inside-a-string-in-php/](https://www.geeksforgeeks.org/how-to-replace-a-word-inside-a-string-in-php/)

给定一个包含一些单词的字符串，任务是替换 PHP 中给定字符串`$str`中出现的所有单词。为了完成这个任务，我们在 PHP 中有以下方法:

## 方法 1: 使用 `str_replace()` 方法

`str_replace()` 方法用于通过替换给定字符串 `$subjectVal` 中的单词 `$searchVal` 来替换其所有出现。

### 语法

```php
str_replace( $searchVal, $replaceVal, $subjectVal, $count )
```

### 示例

```php
<?php
// PHP program to replace all occurence
// of a word inside a string

// Given string
$str = "geeks for Geeks";

// Word to be replaced
$w1 = "geeks";

//  Replaced by
$w2 = "GEEKS";

// Using str_replace() function 
// to replace the word 
$str = str_replace($w1, $w2, $str);

// Printing the result
echo $str; 
?>
```

### 输出

```php
GEEKS for Geeks
```