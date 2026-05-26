# PHP `md5_file()` 函数

> Original: [https://www.geeksforgeeks.org/php-md5_file-function/](https://www.geeksforgeeks.org/php-md5_file-function/)

`md5_file()` 函数是 PHP 中的一个内置函数，用于生成给定文件的 MD5 散列值。此函数在成功时返回字符串，否则返回 `False`。

## 语法

```php
md5_file( $file, $raw )
```

## 参数

此函数接受两个参数，如下所述。

*   `$file`：它是指定文件路径的强制参数。
*   `$raw`：它是一个可选参数，用于指定布尔值。
    *   `true` - 返回原始 16 字符二进制格式。
    *   `false` - 默认值。返回 32 个字符长的十六进制数字。

## 返回值

成功时此函数返回 MD5 散列字符串，否则返回 `False`。

## 程序示例

假设有一个名为 `gfg.txt` 的文件，其内容如下：

> 发表你自己的文章，与世界分享知识！！

以下程序说明了 `md5_file()` 函数：

### 程序 1

```php
<?php
// PHP program to illustrate md5_file()
$gfg = md5_file("gfg.txt");
echo $gfg;
?>
```

发帖主题：Re：Колибри0.7.8.0

```
1d4e50ae1992ad8adf2f7bb6ee4dd0cd
```

### 程序 2

可选参数 `$raw`，值 `TRUE` 和 `FALSE` 不同。

```php
<?php
// PHP program to illustrate md5_file() function

// Without optional parameter
echo md5_file("gfg.txt") . "\n";

// with optional parameter $raw = FALSE (by default)
// no changes in result
echo md5_file("gfg.txt", FALSE) . "\n";

// with optional parameter $raw = TRUE
// result changed
echo md5_file("gfg.txt", TRUE) . "\n";
?>
```

发帖主题：Re：Колибри0.7.8.0

```
1d4e50ae1992ad8adf2f7bb6ee4dd0cd
1d4e50ae1992ad8adf2f7bb6ee4dd0cd
????/{??M??
```

## 引用

[http://php.net/manual/en/function.md5-file.php](http://php.net/manual/en/function.md5-file.php)