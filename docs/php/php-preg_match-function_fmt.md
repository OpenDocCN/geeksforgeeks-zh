# PHP preg_match()函数

> Original: [https://www.geeksforgeeks.org/php-preg_match-function/](https://www.geeksforgeeks.org/php-preg_match-function/)

此函数在字符串中搜索模式，如果模式存在，则返回 `TRUE`，否则返回 `FALSE`。搜索通常从主题字符串的开头开始。可选参数 `offset` 用于指定开始搜索的位置。

## 语法

```php
int preg_match( $pattern, $input, $matches, $flags, $offset )
```

## 参数

此函数接受五个参数，如下所述：

*   `pattern`: 此参数保存要搜索的模式字符串。
*   `input`: 此参数保存输入字符串。
*   `matches`: 如果存在匹配，搜索结果将包含在此数组中。`$matches[0]` 将包含匹配整个模式的文本，`$matches[1]` 将包含匹配第一个捕获的括号子模式的文本，依此类推。
*   `flags`: `flag` 可以是以下值：
    *   `PREG_OFFSET_CAPTURE`: 如果传递此标志，则为每个匹配项返回一个额外的字符串偏移量。
    *   `PREG_UNMATCHED_AS_NULL`: 如果传递此标志，则不匹配的子模式报告为 `NULL`；否则报告为空字符串。
*   `offset`: 通常，搜索从输入字符串的开头开始。此可选参数 `offset` 用于指定从哪个字节位置开始搜索。

## 返回值

如果模式存在，则返回 `TRUE`，否则返回 `FALSE`。

下面的示例说明了 PHP 中的 `preg_match()` 函数：

### 示例 1

此示例接受 `PREG_OFFSET_CAPTURE` 标志。

```php
<?php

// Declare a variable and initialize it
$geeks = 'GeeksforGeeks';

// Use preg_match() function to check match
preg_match('/(Geeks)(for)(Geeks)/', $geeks, $matches, PREG_OFFSET_CAPTURE);

// Display matches result
print_r($matches);

?>
```

**输出：**

```php
Array
(
    [0] => Array
        (
            [0] => GeeksforGeeks
            [1] => 0
        )

    [1] => Array
        (
            [0] => Geeks
            [1] => 0
        )

    [2] => Array
        (
            [0] => for
            [1] => 5
        )

    [3] => Array
        (
            [0] => Geeks
            [1] => 8
        )

)
```

### 示例 2

```php
<?php

// Declare a variable and initialize it
$gfg = "GFG is the best Platform.";

// case-Insensitive search for the word "GFG"
if (preg_match("/\bGFG\b/i", $gfg, $match))
    echo "Matched!";
else
    echo "not matched";

?>
```

**输出：**

```php
Matched!
```

**引用：**[http://php.net/manual/en/function.preg-match.php](http://php.net/manual/en/function.preg-match.php)