# PHP `simplexml_load_file()` 函数

> Original: [https://www.geeksforgeeks.org/php-simplexml_load_file-function/](https://www.geeksforgeeks.org/php-simplexml_load_file-function/)

`simplexml_load_file()` 函数是 PHP 中的一个内置函数，用于将格式良好的 XML 文档转换为给定文件的对象。

## 语法

```php
SimpleXMLElement simplexml_load_file( string $filename, string $class_name = "SimpleXMLElement",
                                    int $options = 0, string $ns = "", bool $is_prefix = FALSE )
```

## 参数

此函数接受上述五个参数，如下所述：

*   `$filename`: 此参数保存文件名的路径。
*   `$class_name`: 可选参数。使用 `simplexml_load_file()` 函数返回指定类的对象。此类扩展了 `SimpleXMLElement` 类。
*   `$options`: 可选参数，用于附加 Libxml 参数。
*   `$ns`: 此参数保存命名空间前缀或 URI。
*   `$is_prefix`: 如果 `ns` 是前缀，则此参数设置为 `true`；如果是 URI，则设置为 `false`。其默认值为 `false`。

## 返回值

此函数返回 `SimpleXMLElement` 类的对象，其属性包含 XML 文档中保存的数据；如果失败，则返回 `false`。

## 示例

下面的程序演示了 PHP 中的 `simplexml_load_file()` 函数：

**gfg.xml 文件：**

```xml
<?xml version="1.0"?>
<organization>
    <name>GeeksforGeeks</name>
    <address>Noida India</address>
    <contact>
        <email>abc@geeksforgeeks.org</email>
        <mobile>+91-987654321</mobile>
    </contact>
</organization>
```

**程序：**

```php
<?php

// Check file exist or not
if (file_exists('gfg.xml')) {

// If XML file exists then
    // load the XML file
    $xml_file = simplexml_load_file('gfg.xml');

// Display the content of XML file
    var_dump($xml_file);

} else {

exit('Fail to open the file');
}
?>
```

发帖主题：Re：Колибри0.7.8.0

**引用：**[https://www.php.net/manual/en/function.simplexml-load-file.php](https://www.php.net/manual/en/function.simplexml-load-file.php)