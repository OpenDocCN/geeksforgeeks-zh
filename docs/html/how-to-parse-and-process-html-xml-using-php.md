# 如何用 PHP 解析和处理 HTML/XML？

> 原文:[https://www . geesforgeks . org/如何解析和处理-html-xml-using-php/](https://www.geeksforgeeks.org/how-to-parse-and-process-html-xml-using-php/)

在本文中，我们将学习如何使用 PHP 处理 XML。我们已经学习了 XML 的基础知识以及它们与 HTML 的区别。可以从 [XML 元素](https://www.geeksforgeeks.org/xml-elements/)中学习不同的 XML 元素，了解以下程序的工作。

[**Simplexml _ load _ string()**](https://www.geeksforgeeks.org/php-simplexml_load_string-function/)函数用于解析给定的 XML，然后 XML 对象可以用于访问 XML 数据。

**示例 1:** 以下示例读取并打印给定的 XML 字符串。

## HTML

```html
<html>

<body>
    <?php
    /* XML string */
    $myXMLData =
    "<?xml version='1.0' encoding='UTF-8'?>
    <note>
        <to>GeeksForGeeks</to>
        <from>Tom</from>
        <heading>Submission</heading>

        <body>
            Please see my articles of PHP!
        </body>
    </note>";

    /* The function reads xml data
       from the passed string */
    $xml = simplexml_load_string($myXMLData)
    or die("Error: Cannot create xml data object");

    print_r($xml);
    ?>
</body>

</html>
```