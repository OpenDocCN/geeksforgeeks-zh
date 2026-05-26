# XMLReader::open() 函数

> 原文：[https://www.geeksforgeeks.org/php-xmlreader-open-function/](https://www.geeksforgeeks.org/php-xmlreader-open-function/)

`XMLReader::open()` 函数是 PHP 中的一个内置函数，用于设置包含要解析的 XML 文档的 URI。简而言之，此函数用于打开需要处理的 XML 文件。

## 语法

```php
bool XMLReader::open( string $URI, string $encoding, int $options )
```

## 参数

此函数接受三个参数，如下所述：

*   `$URI`: 指向文档的 URI。
*   `$encoding` (可选): 指定文档编码或 `NULL`。
*   `$options` (可选): 指代位置掩码。

## 返回值

此函数成功时返回 `TRUE`，失败时返回 `FALSE`。

## 异常

如果静态调用，此函数将抛出 `E_STRICT` 错误。

## 示例

下面的示例说明了 PHP 中的 `XMLReader::open()` 函数：

### 示例 1

**data.xml**

```php
<?xml version="1.0" encoding="utf-8"?>
<body>
    <h1 attrib="value"> Hello </h1>
</body>
```

**index.php**

```php
<?php

// Create a new XMLReader instance
$XMLReader = new XMLReader();

// Load the XML file
$XMLReader->open('data.xml');

// Iterate through the XML
while ($XMLReader->read()) {
    if ($XMLReader->nodeType == XMLREADER::ELEMENT) {

        // Get the value of first attribute
        $value = $XMLReader->getAttributeNo(0);

        // Output the value to browser
        echo $value . "<br>";
    }
}
?>
```

**输出:**

```php
value
```

### 示例 2

**data.xml**

```php
<?xml version="1.0" encoding="utf-8"?>
<body>
    <h1> GeeksforGeeks </h1>
</body>
```

**index.php**

```php
<?php

// Create a new XMLReader instance
$XMLReader = new XMLReader();

// Load the XML file
$XMLReader->open('data.xml');

// Move to the first node
$XMLReader->read();

// Read it as a string
$string = $XMLReader->readString();

// Output the string to the browser
echo $string;
?>
```

**输出:**

```php
GeeksforGeeks
```

## 引用

[https://www.php.net/manual/en/xmlreader.open.php](https://www.php.net/manual/en/xmlreader.open.php)