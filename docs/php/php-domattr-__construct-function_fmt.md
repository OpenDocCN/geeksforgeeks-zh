# PHP DOMAttr::__construct() 函数

> Original: [https://www.geeksforgeeks.org/php-domattr-__construct-function/](https://www.geeksforgeeks.org/php-domattr-__construct-function/)

## 函数介绍

`DOMAttr::__construct()` 函数是 PHP 中的内置函数，用于创建新的 `DOMAttr` 对象。此创建的对象是只读类型。

## 语法

```php
public DOMAttr::__construct( string $name, string $value )
```

## 参数

此函数接受上述两个参数，如下所述：

*   `$name`: 此参数保存属性的元素名称。
*   `$value`: 此参数保存属性的值。

## 示例程序

下面的程序演示了 PHP 中的 `DOMAttr::__construct()` 函数：

### 程序 1

```php
<?php

// Create a new DOMDocument object
$domDocument = new DOMDocument('1.0', 'iso-8859-1');

// Create a root element
$rootElement = new DOMElement('root');

// Append the element as child element 
$element = $domDocument->appendChild($rootElement);

// Create an attribute
$domAttr = new DOMAttr('attr', 'GeeksforGeeks');

// Set the attribute to the node
$attr = $element->setAttributeNode($domAttr);

// Display the XML document
echo $domDocument->saveXML();

?>
```

### 输出

```php
<?xml version="1.0" encoding="iso-8859-1"?>
<root attr="GeeksforGeeks"/>
```

### 程序 2

```php
<?php

// Create a new DOMDocument object
$domDocument = new DOMDocument('1.0', 'iso-8859-1');

// Create a root element
$rootElement = new DOMElement('root');

// Append the element as child element
$element = $domDocument->appendChild($rootElement);

// Create an attribute
$domAttr1 = new DOMAttr('Name', 'GeeksforGeeks');

// Set the attribute to the node
$attr = $element->setAttributeNode($domAttr1);

// Create an attribute
$domAttr2 = new DOMAttr('Address', 'Noida');

// Set the attribute to the node
$attr = $element->setAttributeNode($domAttr2);

// Create an attribute
$domAttr3 = new DOMAttr('mail', 'abc@geeksforgeeks.org');

// Set the attribute to the node
$attr = $element->setAttributeNode($domAttr3);

// Display the XML document
echo $domDocument->saveXML();

?>
```

### 输出

```php
<?xml version="1.0" encoding="iso-8859-1"?>
<root Name="GeeksforGeeks" Address="Noida" mail="abc@geeksforgeeks.org"/>
```

## 引用

[https://www.php.net/manual/en/domattr.construct.php](https://www.php.net/manual/en/domattr.construct.php)