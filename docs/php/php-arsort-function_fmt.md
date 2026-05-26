# PHP `arsort()` 函数

> 原文: [https://www.geeksforgeeks.org/php-arsort-function/](https://www.geeksforgeeks.org/php-arsort-function/)

PHP 中的 `arsort()` 用于根据值对数组进行排序。它的排序方式是保持索引和值之间的关系。默认情况下，它按照值的**降序**排序。

## 语法

```php
bool arsort( $array, $sorting_type )
```

## 参数

该函数接受两个参数，如下所述：

*   `$array`: 此参数指定要排序的数组。这是一个必需参数。
*   `$sorting_type`: 此参数指定用户自定义函数的名称，该函数将用于对数组 `$array` 的键进行排序。此比较函数必须返回一个整数。

## 返回值

该函数成功时返回 `true`，失败时返回 `false`。

下面的程序说明了 PHP 中的 `arsort()` 函数。

## 程序 1

```php
<?php
// PHP program to illustrate
// arsort() function

// Input different array elements
$arr = array("0" => "GeeksforGeeks",
             "1" => "Practice",
             "2" => "Contribute",
             "3" => "Java",
             "4" => "Videos",
             "5" => "Report Bug",
             "6" => "Article",
             "7" => "Sudo Placement"
        );

// Implementation of arsort()
arsort($arr);

// for-Loop  for displaying result
foreach ($arr as $key => $val) {
    echo "[$key] = $val";
    echo"\n";
}

?>
```

### 输出

```php
[4] = Videos
[7] = Sudo Placement
[5] = Report Bug
[1] = Practice
[3] = Java
[0] = GeeksforGeeks
[2] = Contribute
[6] = Article
```

## 程序 2

```php
<?php
// PHP program to illustrate
// arsort() function

// Input different array elements
$arr = array("a" => 11,
             "b" => 22,
             "d" => 33,
             "n" => 44,
             "o" => 55,
             "p" => 66,
             "p" => 77,
             "q" => 88,
        );
// Implementation of arsort()
arsort($arr);

// for-Loop  for displaying result
foreach ($arr as $key => $val) {
    echo "[$key] = $val";
    echo"\n";
}

?>
```

### 输出

```php
[q] = 88
[p] = 77
[o] = 55
[n] = 44
[d] = 33
[b] = 22
[a] = 11
```

## 相关文章

*   [`uksort()` 函数](https://www.geeksforgeeks.org/php-uksort-function/)
*   [`uasort()` 函数](https://www.geeksforgeeks.org/php-uasort-function/)
*   [`usort()` 函数](https://www.geeksforgeeks.org/php-usort-function/)

## 参考

[http://php.net/manual/en/function.arsort.php](http://php.net/manual/en/function.arsort.php)