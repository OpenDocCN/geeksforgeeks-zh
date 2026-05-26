# PHP `substr_replace()` 函数

> Original: [https://www.geeksforgeeks.org/php-substr_replace-function/](https://www.geeksforgeeks.org/php-substr_replace-function/)

`substr_replace()` 函数是 PHP 中的内置函数，用于将一个字符串的一部分替换为另一个字符串。需要将原始字符串中要执行替换的索引作为参数传递。如果需要，还可以指定更换的长度。字符串数组可以作为此函数的参数提供，在这种情况下，替换将依次发生在每个字符串上。

## 语法

```php
substr_replace($string, $replacement, $start, $length)
```

## 参数

此函数接受四个参数，如上面的语法所示，其中前三个参数是必需的，最后一个参数是可选的。所有这些参数如下所述：

*   `$string`：此参数是必需的。它指定要在其中进行替换的输入字符串。
*   `$replacement`：此参数也是必需的。它指定要插入 `$string` 中的字符串。
*   `$start`：此参数也是必需的。它指定需要开始更换的位置。
    *   如果 `$start` 是正数，则替换从字符串中的指定位置开始。
    *   如果 `$start` 是负数，则从字符串的结尾的指定位置开始替换。
    *   如果 `$start` 为 0，则从字符串的第一个字符开始替换。
*   `$length`：此参数是可选的。它指定应该替换多少个字符。如果未指定 `$length`，则替换将在 `$string` 的末尾停止。
    *   如果 `$length` 为正，则表示要替换的 `$string` 部分的长度。
    *   如果 `$length` 为负，则表示从 `$string` 末尾开始需要停止替换的字符数。
    *   如果 `$length` 为 0，则执行插入而不是替换。

## 返回值

返回替换后生成的字符串。如果是字符串数组，则返回该数组。

例如：

```php
Input : $string = "Geeks for Geeks", $replacement = "GFG", $start = 0
Output : GFG

Input : $string = "Hello World", $replacement = "Hello", $start = 6
Output : Hello Hello
```

下面的程序演示了 `substr_replace()` 函数：

### 程序 1

在此程序中，我们将使用不带任何 `$length` 参数的 `substr_replace()` 函数。从 `$start` 到 `$string` 结尾的所有字符都将替换为 `$replacement`。

```php
<?php

echo substr_replace("Hello World", "GFG", 6);

?>
```

输出

```php
Hello GFG
```

### 程序 2

在此程序中，我们将使用 `$length` 设置为 0 的 `substr_replace()` 函数。在这种情况下，将发生插入。不会进行任何替换。

```php
<?php

echo substr_replace("Contribute GFG", "to ", 11, 0);

?>
```

输出

```php
Contribute to GFG
```

### 程序 3

在此程序中，我们将使用 `substr_replace()` 函数，并将 `$length` 设置为正值。在这种情况下，`$replacement` 字符串将替换 `$start` 中最多 `$length` 的 `$string` 字符。

```php
<?php

echo substr_replace("alone", "ph", 0, 2);

?>
```

输出

```php
phone
```

### 程序 4

在此程序中，我们将使用 `substr_replace()` 函数，并将 `$length` 设置为负值。在这种情况下，`$replacement` 字符串将替换 `$string` 中 `$start` 的字符，并在从字符串末尾开始的 `$length` 字符数之前停止。

```php
<?php

echo substr_replace("alone", "ph", 0, -3);

?>
```

输出

```php
phone
```

### 程序 5

在此程序中，我们将使用 `substr_replace()` 函数，不带任何 `$length` 参数，并将 `$start` 设置为负值。替换将从字符串末尾的指定位置开始。

```php
<?php

echo substr_replace("alpha", "one", -3);

?>
```

输出

```php
alone
```

**引用：**[http://php.net/manual/en/function.substr-replace.php](http://php.net/manual/en/function.substr-replace.php)