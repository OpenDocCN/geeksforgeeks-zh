# 在 JavaScript 中将字符串转换为整数

原文: [https://www.geeksforgeeks.org/convert-a-string-to-an-integer-in-javascript/](https://www.geeksforgeeks.org/convert-a-string-to-an-integer-in-javascript/)

在 JavaScript 中，[`parseInt()`](https://www.geeksforgeeks.org/javascript-parseint-function/) 函数用于将字符串转换为整数。该函数返回一个基数为的整数，该整数在 `parseInt()` 函数的第二个参数中指定。当字符串不包含数字时，`parseInt()` 函数返回 `NaN`（不是数字）。

## 语法

```
parseInt(value, radix)
```

它接受字符串作为值，并将其转换为指定的基数系统，然后返回一个整数。

## 示例-1：将字符串转换为整数的程序

```
<script>
function convertStoI() {
    var a = "100";
    var b = parseInt(a);
    document.write("Integer value is" + b);
    var d = parseInt("3 11 43");
    document.write("</br>");
    document.write('Integer value is ' + d);
}
convertStoI();
</script>
```

### 输出

```
Integer value is100
Integer value is 3
```

`parseInt()` 函数将任何基数中的数字转换为十进制。它解析字符串并进行转换，直到它面对字符串文本并停止解析。

## 示例-2

```
<script>
function convertStoI() {
    var r = parseInt("1011", 2);
    var k = parseInt("234", 8);
    document.write('Integer value is ' + r);
    document.write("<br>");
    document.write("integer value is " + k);
    document.write("<br>");
    document.write(parseInt("528GeeksforGeeks"));
}
convertStoI();
</script>
```

### 输出

```
Integer value is 11
integer value is 156
```

JavaScript 最出名的是网页开发，但它也用于各种非浏览器环境。您可以通过以下 [JavaScript 教程](https://www.geeksforgeeks.org/javascript-tutorial/) 和 [JavaScript 示例](https://www.geeksforgeeks.org/javascript-examples/) 从头开始学习 JavaScript。