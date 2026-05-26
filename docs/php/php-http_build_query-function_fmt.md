# PHP http_build_query() 函数

> Original: [https://www.geeksforgeeks.org/php-http_build_query-function/](https://www.geeksforgeeks.org/php-http_build_query-function/)

`http_build_query()` 函数是 PHP 中的一个内置函数，用于从关联（或索引）数组生成 URL 编码的查询字符串。

## 语法

```php
string http_build_query( $query_data, $numeric_prefix, $arg_separator, $enc_type = PHP_QUERY_RFC1738 )
```

## 参数

此函数接受上述四个参数，如下所述：

### `$query_data`
此参数保存一个数组或对象，其中包含以下属性：
*   它可以是一个一维数组或多维数组。
*   如果 `$query_data` 是一个对象，则只有公共属性会被合并到结果中。

### `$numeric_prefix`
如果在基础数组中使用数字索引，此参数将仅优先于基础数组中元素的数字索引。

### `$arg_separator`
它用于分隔参数，但可以通过指定此参数来覆盖。

### `$enc_type`
默认值是 `PHP_QUERY_RFC1738`。

## 返回值
它返回 URL 编码的字符串。

## 示例

下面的程序演示了 PHP 中的 `http_build_query()` 函数：

### 程序 1

```php
<?php
$info = array(
    'sudo' => 'placement',
    'CPP' => 'course',
    'FORK' => 'C',
);

echo http_build_query($info) . "#";
echo http_build_query($info, '', '&');

?>
```

### 输出

```php
sudo=placement&CPP=course&FORK=C#sudo=placement&CPP=course&FORK=C
```

### 程序 2

```php
<?php
$info = array('geeks', 'gfg' => 'sudo', 'placement' => 'hypertext processor');

echo http_build_query($info) . "{content}quot;;
echo http_build_query($info, 'myvar_');
?>
```

### 输出

```php
0=geeks&gfg=sudo&placement=hypertext+processor$myvar_0=geeks&gfg=sudo&placement=hypertext+processor
```

## 引用
[http://docs.php.net/manual/da/function.http-build-query.php](http://docs.php.net/manual/da/function.http-build-query.php)