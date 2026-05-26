# fstat()函数

> Original: [https://www.geeksforgeeks.org/php-fstat-function/](https://www.geeksforgeeks.org/php-fstat-function/)

PHP 中的`fstat()`函数是一个内置函数，用于返回有关打开的文件的信息。文件名作为参数发送给`fstat()`函数，它返回一个包含以下元素的数组：

| 数字索引 | 关联键名 | 描述 |
| --- | --- | --- |
| 0 | dev | 设备号 |
| 1 | ino | Inode number * |
| 2 | mode | Inode protection mode |
| 3 | nlink | Number of links |
| 4 | uid | Owner |
| 5 | gid | Group owner |
| 6 | rdev | Device type, if the Inode device |
| 7 | size | Byte size |
| 8 | atime | Last access time (Unix timestamp) |
| 9 | mtime | Last modification time (Unix timestamp) |
| 10 | ctime | Time when the Inode was last changed (Unix timestamp) |
| 11 | blksize | File system IO block size * * |
| 12 | blocks | Number of 512-byte blocks allocated |

函数的作用是：收集文件指针句柄打开的文件的统计信息。`fstat()`函数类似于`stat()`函数，不同之处在于它操作的是打开的文件指针，而不是文件名。

## 语法

```php
array fstat ( $file )
```

## 参数

PHP 中的`fstat()`函数只接受一个参数。

*   `$file`: 指定要操作的文件句柄。

## 返回值

如果成功，则返回包含上述元素的数组。

## 异常

*   The result of this function varies from server to server. The array can contain a numeric index and / or a name index.
*   The `fstat()` function is similar to the `stat()` function, except that it must open a file.
*   The atime element is not updated with simple file read access.

## 示例程序

以下程序说明了`fstat()`函数：

### 程序 1

```php
<?php
// Opening a file
$myfile = fopen("gfg.txt", "r");

// printing the stats of the opened file
print_r(fstat($myfile));

// closing the file
fclose($myfile);
?>
```

帖子主题：Re：Колибри

### 程序 2

```php
<?php
// Opening a file
$myfile = fopen("gfg.txt", "r");

// printing the associative part of the output array
$mystat = fstat($myfile);
print_r(array_slice($mystat, 13));

// closing the file
fclose($myfile);
?>
```

帖子主题：Re：Колибри

## 引用

[http://php.net/manual/en/function.fstat.php](http://php.net/manual/en/function.fstat.php)