# PHP `mb_str_split()` 函数

> Original: [https://www.geeksforgeeks.org/php-mb_str_split-function/](https://www.geeksforgeeks.org/php-mb_str_split-function/)

`mb_str_split()` 函数是在 PHP 版本 7.4.0 中引入的，只有等于或高于 7.4.0 的 PHP 版本才支持该函数。函数的作用是：替代 `str_split()` 函数。它用于拆分具有指定块长度的给定字符串，成功时返回数组，失败时返回 `False`，但在 PHP 8 中，失败时不返回 `False`。

## `语法：`

```php
array mb_str_split(string $string, int $length, string $encoding)
```

## `参数：`

| `名称` | `类型` | `描述` |
| :--- | :--- | :--- |
| `$STRING` | String | 要拆分的字符串，必需。 |
| `$Length` | Int | 用于拆分字符串的子字符串长度。可选参数。 |
| `$coding` | String | 应用于子字符串的编码格式。可选参数，默认为 `NULL`。 |

## `示例 1：`
在下面的示例中，单词 `"Awesome"` 正在使用 `mb_str_split()` 函数进行拆分，由于此函数返回一个字符数组，因此已使用 `print_r()` 来打印输出。

```php
<?php

print_r(mb_str_split("Awesome"));
?>
```

发帖主题：Re：Колибри0.7.8.0

## `示例 2：`
在下面的示例中，创建了两个变量 `$sentence` 和 `$word`。`$sentence` 用于存储任何字符串类型的随机语句，而 `$word` 用于存储 `mb_str_split()` 返回的数组。该代码的基本思想是将 `"GeeksforGeeks"` 从存储在 `$sentence` 中的句子中分离出来。这里，`mb_str_split()` 用于分隔指定长度的子字符串，数组存储在 `$word` 中，并相应地显示结果。

```php
<?php

$sentence = "GeeksforGeeks is Awesome";

$word = mb_str_split($sentence,13);
echo $word[0];

?>
```

发帖主题：Re：Колибри0.7.8.0

**引用：**[https://www.php.net/manual/en/function.mb-str-split.php](https://www.php.net/manual/en/function.mb-str-split.php)