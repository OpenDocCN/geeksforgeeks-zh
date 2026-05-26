# PHP XMLReader::moveToAttributeNs() 函数

> Original: [https://www.geeksforgeeks.org/php-xmlreader-movetoattributens-function/](https://www.geeksforgeeks.org/php-xmlreader-movetoattributens-function/)

`XMLReader::moveToAttributeNs()` 函数是 PHP 中的一个内置函数，用于将光标移动到指定命名空间中的命名属性上。当我们想要获取特定命名空间中特定属性的属性值并忽略所有其他命名空间时，此方法非常有用。

## 语法

```php
bool XMLReader::moveToAttributeNs( string $localName, string $namespaceURI )
```

## 参数

此函数接受上述两个参数，如下所述：

*   `$localName`：它指定属性的本地名称。
*   `$namespaceURI`：它指定命名空间 URI。

## 返回值

此函数成功时返回 `TRUE`，失败时返回 `FALSE`。

## 示例

下面给出的程序演示了 PHP 中的 `XMLReader::moveToAttributeNs()` 函数：

### 示例 1（错误命名空间）

XML 文件 (`data.xml`)：

```xml
<?xml version="1.0" encoding="utf-8"?>
<div xmlns:z="my_namespace">
    <z:h1 z:attrib="value"> Foo Bar </z:h1>
</div>
```

PHP 文件 (`index.php`)：

```php
<?php

// Create a new XMLReader instance
$XMLReader = new XMLReader();

// Open the XML file
$XMLReader->open('data.xml');

// Iterate through the XML nodes
// to reach the h1 node
$XMLReader->read();
$XMLReader->read();
$XMLReader->read();

// Move to attribute with name attrib
// with the namespace "my_namespace"
$XMLReader->moveToAttributeNs("attrib", "wrong_namespace");

// Output the value to browser
echo $XMLReader->value;
?>
```

输出：

```php
// Empty string because there is no namespace called "wrong_namespace"
```

### 示例 2（正确命名空间）

XML 文件 (`data.xml`)：

```xml
<?xml version="1.0" encoding="utf-8"?>
<div xmlns:z="my_namespace">
    <z:h1 z:attrib="value"> Foo Bar </z:h1>
</div>
```

PHP 文件 (`index.php`)：

```php
<?php

// Create a new XMLReader instance
$XMLReader = new XMLReader();

// Open the XML file
$XMLReader->open('data.xml');

// Iterate through the XML nodes
// to reach the z:h1 node
$XMLReader->read();
$XMLReader->read();
$XMLReader->read();

// Move to attribute with name attrib
// with the namespace "my_namespace"
$XMLReader->moveToAttributeNs("attrib", "my_namespace");

// Output the value to browser
echo $XMLReader->value;
?>
```

输出：

```php
value
```

**引用：** [https://www.php.net/manual/en/xmlreader.movetoattributens.php](https://www.php.net/manual/en/xmlreader.movetoattributens.php)