# 如何用 PHP 写文件？

> 原文：[https://www.geeksforgeeks.org/how-to-write-into-a-file-in-php/](https://www.geeksforgeeks.org/how-to-write-into-a-file-in-php/)

在本文中，我们将讨论如何使用 PHP 内置的 [`fwrite()`](https://www.geeksforgeeks.org/php-fwrite-function/) 函数写入文本文件。

## fwrite() 函数

`fwrite()` 函数用于写入给定文件。它会在文件的末尾或达到作为参数传递的指定长度时停止，以先到者为准。

### 语法

```php
fwrite(file_name, string)
```

- `File name`：输入文件的名称。
- `String`：要写入的内容。

**返回值：** 成功时返回写入字节数，失败时返回 `false`。

## 示例 1

```php
<?php
// Open a file named geeks_data in write mode
$data = fopen("geeks_data.txt", "w");

// writing content to a file using fwrite() function
echo fwrite($data, "This data is added as extra");

// closing the file
fclose($data);
?>
```

**输出：**

```php

```

## 示例 2

```php
<?php
// Open a file named geeks_data in write mode
$data = fopen("geeks_data.txt", "w");

// writing content to a file using fwrite() function
echo fwrite($data, "This data is added as extra 
                    along with previous data");

// closing the file
fclose($data);
?>
```

**输出：**

```php

```