# PHP `fSeek()` 函数

> Original: [https://www.geeksforgeeks.org/php-fseek-function/](https://www.geeksforgeeks.org/php-fseek-function/)

PHP 中的 `fSeek()` 函数是一个内置函数，用于在打开的文件中查找。它将文件指针从其当前位置向前或向后移动到由字节数指定的新位置。文件和偏移量作为参数发送给 `fSeek()` 函数，如果成功则返回 0，如果失败则返回 -1。

## 语法

```php
int fseek ( $file, $offset, $whence)
```

## 参数

PHP 中的 `fSeek()` 函数接受三个参数，如下所述。

*   `$file`：指定文件所需的参数。
*   `$offset`：指定指针新位置的强制参数。它以文件开头的字节为单位进行测量。
*   `$whence`：这是一个可选参数，可以具有以下可能的值：
    *   `SEEK_SET`：将位置设置为等于偏移量。
    *   `SEEK_CUR`：将位置设置为当前位置加上偏移量。
    *   `SEEK_END`：将位置设置为 EOF 加上偏移量。要移动到 EOF 之前的位置，偏移量必须为负数。

## 返回值

成功返回 0，失败返回 -1。

## 异常

*   查找过去的 EOF（文件结尾）会生成错误。
*   如果文件是在追加（`a` 或 `a+`）模式下打开的，则无论文件位置如何，写入该文件的任何数据都将被追加，并且调用 `fSeek()` 的结果将是未定义的。
*   并不是所有的流都支持查找。对于那些不支持搜索的人，从当前位置向前搜索是通过读取和丢弃数据来完成的；其他形式的搜索将失败。

## 程序示例

下面的程序说明了 PHP 中的 `fSeek()` 函数：

### 程序 1

在以下程序中，名为 `gfg.txt` 的文件包含以下内容：

> Geeksforgeek 是极客的门户！

```php
<?php
// Opening a file
$myfile = fopen("gfg.txt", "w");

// reading first line
fgets($myfile);

// moving back to the beginning of the file
echo fseek($myfile, 0);

// closing the file
fclose($myfile);
?>
```

### 程序 2

在下面程序中，名为 `gfg.txt` 的文件包含以下内容：

> Geeksforgeek 是极客的门户！

```php
<?php
// Opening a file
$myfile = fopen("gfg.txt", "w");

// reading first line
fgets($myfile);

// fseek() pointing to the end of the file
fseek($fp, 0, SEEK_END);

// closing the file
fclose($myfile);
?>
```

## 引用

[http://php.net/manual/en/function.fseek.php](http://php.net/manual/en/function.fseek.php)