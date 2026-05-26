# PHP DOMNode::C14NFile() 函数

> Original: [https://www.geeksforgeeks.org/php-domnode-c14nfile-function/](https://www.geeksforgeeks.org/php-domnode-c14nfile-function/)

`DOMNode::C14NFile()` 函数是 PHP 中的一个内置函数，用于将节点规范化为文件。

## 语法

```php
int DOMNode::C14NFile( string $uri, bool $exclusive, bool $with_comments, array $xpath, array $ns_prefixes )
```

## 参数

此函数接受五个参数，如下所述：

*   `$uri` (可选)：指定写入输出的路径。
*   `$exclusive` (可选)：指定是否仅为匹配提供的 XPath 或命名空间前缀的节点启用独占解析。
*   `$with_comments` (可选)：指定是否在输出中保留注释。
*   `$xpath` (可选)：指定用于过滤节点的 XPath 数组。
*   `$ns_prefixes` (可选)：指定用于过滤节点的命名空间前缀数组。

## 返回值

此函数返回写入的字节数，失败时返回 `FALSE`。

## 示例

以下示例说明 PHP 中的 `DOMNode::C14NFile()` 函数：

### 示例 1

在此示例中，我们将字符串形式的 DOM 内容保存到不带注释的文件。

```php
<?php

// Create a DOMDocument
$doc = new DOMDocument();

// Load XML
$doc->loadXML('<html></html>');

// Create an heading element on DOMDocument object
$h1 = $doc->createElement('h1');

// Append the child
$doc->documentElement->appendChild($h1);

// Save the data without comments
$stringdata = $doc->C14NFile('new.txt');
?>
```

**输出：** 这将创建一个名为 `new.txt` 的文件，具有以下文本内容：

```php
<html><h1></h1></html>
```

### 示例 2

在本例中，我们将字符串形式的 DOM 内容保存到一个带有注释的文件中。

```php
<?php

// Create a DOMDocument
$doc = new DOMDocument();

// Load XML
$doc->loadXML('<html><!-- This is a comment --></html>');

// Create an heading element on DOMDocument object
$h1 = $doc->createElement('h1');

// Append the child
$doc->documentElement->appendChild($h1);

// Save the data with comments
$stringdata = $doc->C14NFile('new.txt', false, true);
?>
```

**输出：** 这将创建一个名为 `new.txt` 的文件，具有以下文本内容：

```php
<html><!-- This is a comment --><h1></h1></html>
```

## 引用

[https://www.php.net/manual/en/domnode.c14nfile.php](https://www.php.net/manual/en/domnode.c14nfile.php)