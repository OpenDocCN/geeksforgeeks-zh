# HTML DOM 匹配()方法

> 原文:[https://www.geeksforgeeks.org/html-dom-matches-method/](https://www.geeksforgeeks.org/html-dom-matches-method/)

**匹配()**方法检查所提供的**选择器字符串**选择的元素是否是选择器。如果指定的元素是有效的选择器，那么它将返回**真，**否则**假**。

**语法:**

```html
var boolean_result = element.matches("selector");
```

**参数:**这里，**选择器**作为参数。

**返回值:**返回**布尔值**(即选择器匹配其他**时为**真**假**)。

**示例:**在本例中，有一个列表，其中有一些元素的类选择器为**号**。因此，我们将列表存储在一个变量中，通过对列表进行迭代，如果**选择器匹配数字**类，则相应地在文档上打印。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        HTML DOM matches() Method
    </title>
</head>

<body>
    <h1>GeeksforGeeks</h1>

    <ul id="abc">
        <li>A</li>
        <li class="number">1</li>
        <li>C</li>
        <li class="number">2</li>
    </ul>

    <script>
        var abc = document.getElementsByTagName('li');
        for (var i = 0; i < abc.length; i++) {
            if (abc[i].matches('.number')) {
                document.write(abc[i].textContent 
                    + ' is not an alphabet ,  ');
            }
        }
    </script>
</body>

</html>
```

**输出:**

![](img/21d8be3dfba24d587164c29fd7fd6add.png)

**注意:**所有浏览器都支持。