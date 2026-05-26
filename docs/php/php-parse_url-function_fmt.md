# PHP `parse_url()` 函数

> Original: [https://www.geeksforgeeks.org/php-parse_url-function/](https://www.geeksforgeeks.org/php-parse_url-function/)

`parse_url()` 函数是 PHP 中的一个内置函数，用于通过解析返回 URL 的组件。它解析 URL 并返回包含其各种组件关联数组。

## 语法

```php
parse_url( $url, $component = -1 )
```

## 参数

此函数接受上述两个参数，如下所述：

*   `url`: 此参数持有要解析的 URL。无效字符会被替换为 `_`（下划线）。
*   `component`: 此参数指定返回 URL 的哪个组件（`PHP_URL_SCHEME`、`PHP_URL_HOST`、`PHP_URL_PORT`、`PHP_URL_USER`、`PHP_URL_PASS`、`PHP_URL_PATH`、`PHP_URL_QUERY` 或 `PHP_URL_FRAGMENT`）作为字符串。

## 返回值

*   如果省略 `component` 参数，则返回一个关联数组。
*   如果指定了 `component` 参数，则返回一个字符串。
*   如果参数是格式错误的 URL，则返回 `FALSE`。

以下示例说明了 PHP 中 `parse_url()` 函数的使用：

## 示例 1

```php
<?php

// Declare a variable and initialize it with URL
$url = 'http://geeksforgeeks.org/php/#basics';

// Use parse_url() function to parse the URL
var_dump(parse_url($url));
var_dump(parse_url($url, PHP_URL_SCHEME));

?>
```

**输出：**

```php
array(4) {
  ["scheme"]=>
  string(4) "http"
  ["host"]=>
  string(17) "geeksforgeeks.org"
  ["path"]=>
  string(5) "/php/"
  ["fragment"]=>
  string(6) "basics"
}
string(4) "http"
```

## 示例 2

```php
<?php

// Declare a variable and initialize it with URL
$url = '//www.geeksforgeeks.org/path?php=PHP';

// Use parse_url() function to
// parse the URL
var_dump(parse_url($url));

?>
```

**输出：**

```php
array(3) {
  ["host"]=>
  string(21) "www.geeksforgeeks.org"
  ["path"]=>
  string(5) "/path"
  ["query"]=>
  string(7) "php=PHP"
}
```

**引用：** [http://php.net/manual/en/function.parse-url.php](http://php.net/manual/en/function.parse-url.php)