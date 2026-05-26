# PHP preg_replace() 函数

> Original: [https://www.geeksforgeeks.org/php-preg_replace-function/](https://www.geeksforgeeks.org/php-preg_replace-function/)

`preg_replace()` 函数是 PHP 中的一个内置函数，用于执行正则表达式以搜索和替换内容。

## 语法

```php
preg_replace( $pattern, $replacement, $subject, $limit, $count )
```

## 参数

此函数接受上述五个参数，如下所述。

*   `$pattern`: 此参数包含用于搜索内容的字符串元素，可以是一个字符串或字符串数组。
*   `$replacement`: 必填参数，指定要替换的字符串或包含字符串的数组。
*   `$subject`: 要搜索和替换的字符串或包含字符串的数组。
*   `$limit`: 此参数指定每个模式的最大可能替换次数。
*   `$count`: 可选参数。此变量将填充已完成的替换次数。

## 返回值

如果 `$subject` 参数是数组，则此函数返回数组，否则返回字符串。

下面的程序演示了 PHP 中的 `preg_replace()` 函数：

### 程序 1

```php
<?php

// PHP program to illustrate 
// preg_replace function

$string = 'November 01, 2018';
$pattern = '/(\w+) (\d+), (\d+)/i';
$replacement = '${1} 02, $3';

// print output of function
echo preg_replace($pattern, $replacement, $string);
?>
```

### 输出

```php
November 02, 2018
```

### 程序 2

```php
<?php

// PHP program to illustrate 
// preg_replace function
$subject = array('1', 'GFG', '2',
'Geeks', '3', 'GCET', 'Contribute', '4'); 
$pattern = array('/\d/', '/[a-z]/', '/[1a]/'); 
$replace = array('X:$0', 'Y:$0', 'Z:$0');

// Print Result return by function
echo "preg_replace returns\n";
print_r(preg_replace($pattern, $replace, $subject)); 
?>
```

### 输出

```php
preg_replace returns
Array
(
    [0] => X:Z:1
    [1] => GFG
    [2] => X:2
    [3] => GY:eY:eY:kY:s
    [4] => X:3
    [5] => GCET
    [6] => CY:oY:nY:tY:rY:iY:bY:uY:tY:e
    [7] => X:4
)
```

### 程序 3

```php
<?php

// PHP program to illustrate 
// preg_replace function
$count = 0;

// Display result after replace and count 
echo preg_replace(array('/\d/', '/\s/'),
        '*', 'Geeks 4 Geeks', -1, $count);
echo "\n" . $count;
?>
```

### 输出

```php
Geeks***Geeks
```

**引用：** [http://php.net/manual/en/function.preg-replace.php](http://php.net/manual/en/function.preg-replace.php)