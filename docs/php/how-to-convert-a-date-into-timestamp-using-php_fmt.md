# 如何用 PHP 将日期转换成时间戳？

> 原文:[https://www . geeksforge . org/如何使用-php/](https://www.geeksforgeeks.org/how-to-convert-a-date-into-timestamp-using-php/) 将日期转换为时间戳

任务是使用 PHP 将日期转换为时间戳。这个任务可以使用 PHP 中的`strtotime()`函数来完成。它用于将英文文本日期时间描述转换为 UNIX 时间戳。Unix 时间戳表示特定日期和 UNIX 纪元之间的秒数。

**语法:**

```php
strtotime ($EnglishDateTime, $time_now)
```

**示例:**

## 服务器端编程语言（Professional Hypertext Preprocessor 的缩写）

```php
// PHP program to convert the date 
// to timestamp 
<?php

$date = "2020-09-23";
$timestamp1 = strtotime($date);
echo $timestamp1; 
echo "<br>";

$date2 = "24-09-2020";
$timestamp2 = strtotime($date2);
echo $timestamp2; 
echo "<br>";

$date3 = "16 May 2019";
$timestamp3 = strtotime($date3);
echo $timestamp3;
?>
?>
```

**输出:**

```php

```