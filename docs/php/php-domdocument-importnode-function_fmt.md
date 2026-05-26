# PHP DOMDocument::importNode() 函数

> Original: [https://www.geeksforgeeks.org/php-domdocument-importnode-function/](https://www.geeksforgeeks.org/php-domdocument-importnode-function/)

`DOMDocument::importNode()` 函数是 PHP 中的一个内置函数，用于返回需要导入的节点的副本，并将其与当前文档相关联。

## 语法

```php
DOMNode DOMDocument::importNode( DOMNode $importedNode, bool $deep = FALSE )
```

## 参数

此函数接受上述两个参数，如下所述：

*   `$importedNode`: 此参数保存需要导入的节点。
*   `$deep`: 此参数持有布尔值。如果设置为 `true`，它将递归地导入导入节点下的子树。

## 返回值

如果无法复制，则此函数返回成功或 `false` 的复制节点。

下面的程序演示了 PHP 中的 `DOMDocument::importNode()` 函数：

## 程序

```php
<?php

// Create a new document
$dom = new DOMDocument;

// Load the XML document
$dom->loadXML("<root><contact><email>abc@geeksforgeeks.org</email>
<mobile>+91-987654321</mobile></contact></root>");

// Use getElementsByTagName() function to search
// all elements with given local tag name
$node = $dom->getElementsByTagName("contact")->item(0);

// Create a new document
$dom1 = new DOMDocument;

$dom1->formatOutput = true;

// Load the XML document
$dom1->loadXML("<root><contactinfo><email>abc@geeksforgeeks.org</email>
<mobile>+91-987654321</mobile></contactinfo></root>");

echo "Document before copying the nodes\n";

// Save the file in XML and display it
echo $dom1->saveXML();

// Use importNode() function to import the node
$node = $dom1->importNode($node, true);

// Append child to the document
$dom1->documentElement->appendChild($node);

echo "\nDocument after copying the nodes\n";

// Save XML document and display it
echo $dom1->saveXML();

?>
```

## 输出

```php
Document before copying the nodes
<?xml version="1.0"?>
<root>
    <contactinfo><email>abc@geeksforgeeks.org</email>
    <mobile>+91-987654321</mobile></contactinfo>
</root>
Document after copying the nodes
<?xml version="1.0"?>
<root>
    <contactinfo><email>abc@geeksforgeeks.org</email>
    <mobile>+91-987654321</mobile></contactinfo>
    <contact><email>abc@geeksforgeeks.org</email>
    <mobile>+91-987654321</mobile></contact>
</root>
```

## 引用

[https://www.php.net/manual/en/domdocument.importnode.php](https://www.php.net/manual/en/domdocument.importnode.php)