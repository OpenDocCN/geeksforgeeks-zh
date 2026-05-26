# PHP `ksort()` 函数

> Original: [https://www.geeksforgeeks.org/php-ksort-function/](https://www.geeksforgeeks.org/php-ksort-function/)

`ksort()` 函数是 PHP 中的一个内置函数，用于根据数组的键值按**升序**对数组进行排序。它以保持索引和值之间的关系的方式进行排序。

## 语法

```php
bool ksort( $array, $sorting_type )
```

## 参数

此函数接受上述两个参数，如下所述：

*   `$array`：此参数指定要排序的数组。这是一个必需参数。
*   `$sorting_type`：这是一个可选参数。下面讨论了不同的排序类型：
    *   `SORT_REGULAR`：如果 `$sorting_type` 的值是 `SORT_REGULAR`，则正常比较项目。
    *   `SORT_NUMERIC`：如果 `$sorting_type` 的值是 `SORT_NUMERIC`，则以数字方式比较项目。
    *   `SORT_STRING`：如果 `$sorting_type` 的值是 `SORT_STRING`，则将项目作为字符串进行比较。
    *   `SORT_LOCALE_STRING`：如果 `$sorting_type` 的值是 `SORT_STRING`，则根据当前区域设置将项目作为字符串进行比较。

## 返回值

此函数成功时返回 `True`，失败时返回 `False`。

下面的程序演示了 PHP 中的 `ksort()` 函数。

## 程序 1

```php
<?php
// PHP program to illustrate
// ksort() function

// Input different array elements
$arr = array("13" =>"ASP.Net",
             "12" =>"C#",
             "11" =>"Graphics",
             "4" =>"Video Editing",
             "5" =>"Photoshop",
             "6" =>"Article",
             "4" =>"Placement",
             "8" =>"C++",
             "7" =>"XML",
             "10" =>"Android",
             "1" =>"SQL",
             "2" =>"PL/Sql",
             "3" =>"End",
             "0" =>"Java",       
        );

// Implementation of ksort()
ksort($arr);

// for-Loop for displaying result
foreach ($arr as $key => $val) {
    echo "[$key] = $val";
    echo"\n";
}

?>
```

## 输出

```php
[0] = Java
[1] = SQL
[2] = PL/Sql
[3] = End
[4] = Placement
[5] = Photoshop
[6] = Article
[7] = XML
[8] = C++
[10] = Android
[11] = Graphics
[12] = C#
[13] = ASP.Net
```

## 程序 2

```php
<?php
// PHP program to illustrate
// ksort function

// Input different array elements
$arr = array("z" => 11,
             "y" => 22,
             "x" => 33,
             "n" => 44,
             "o" => 55,
             "b" => 66,
             "a" => 77,
             "m" => 2,
             "q" => -11,
             "i" => 3,
             "e" => 56,
             "d" => 1,                                    
        );

// Implementation of ksort
ksort($arr);

// for-Loop for displaying result
foreach ($arr as $key => $val) {
    echo "[$key] = $val";
    echo"\n";
}

?>
```

## 输出

```php
[a] = 77
[b] = 66
[d] = 1
[e] = 56
[i] = 3
[m] = 2
[n] = 44
[o] = 55
[q] = -11
[x] = 33
[y] = 22
[z] = 11
```

## 相关文章

*   [`asort()` function](https://www.geeksforgeeks.org/php-asort-function/)
*   [`uksort()` function](https://www.geeksforgeeks.org/php-uksort-function/)
*   [`usort()` function](https://www.geeksforgeeks.org/php-usort-function/)

## 引用

[http://php.net/manual/en/function.ksort.php](http://php.net/manual/en/function.ksort.php)