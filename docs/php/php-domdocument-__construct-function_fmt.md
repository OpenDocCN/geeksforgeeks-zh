# PHP DOMDocument::__construct() 函数

> Original: [https://www.geeksforgeeks.org/php-domdocument-__construct-function/](https://www.geeksforgeeks.org/php-domdocument-__construct-function/)

`DOMDocument::__construct()` 函数是 PHP 中的内置函数，用于创建新的 `DOMDocument` 对象。

## 语法

```php
public DOMDocument::__construct( string $version, string $encoding )
```

## 参数

此函数接受上述两个参数，如下所述：

*   `$version`: 此参数将文档的版本保存为 XML 声明的一部分。
*   `$encoding`: 此参数将文档编码保存为 XML 声明的一部分。

## 示例

下面的程序演示了 PHP 中的 `DOMDocument::__construct()` 函数：

### 程序 1

```php
<?php

// Create new DOMDocument
$dom = new DOMDocument('1.0', 'iso-8859-1');

// Display the output
echo $dom->saveXML();

?>
```

**输出：**

```php
<?xml version="1.0" encoding="iso-8859-1"?>

```

### 程序 2

```php
<?php

// Create new DOMDocument
$dom = new DOMDocument('1.0', 'iso-8859-1');

// Set xmlStandalone() function to True
$dom->xmlStandalone = "true";

// Display the output
echo $dom->saveXML();

?>
```

**输出：**

```php
<?xml version="1.0" encoding="iso-8859-1" standalone="no"?>

```

## 引用

[https://www.php.net/manual/en/domdocument.construct.php](https://www.php.net/manual/en/domdocument.construct.php)