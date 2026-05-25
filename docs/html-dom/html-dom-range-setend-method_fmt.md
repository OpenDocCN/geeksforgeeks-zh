# HTML DOM Range setEnd()方法

> 原文：[https://www.geeksforgeeks.org/html-dom-range-setend-method/](https://www.geeksforgeeks.org/html-dom-range-setend-method/)

`setEnd()`方法用于设置`Range`的结束位置。

`endNode`可以是文本节点、子节点等。`endOffset`可以是`endNode`的字符数，也可以是`endNode`的子节点的数量。

## 语法

```html
range.setEnd(endNode, endOffset);
```

## 参数

该方法接受两个参数：

*   `endNode`：用于设置范围结束的节点。
*   `endOffset`：此参数是大于或等于零的偏移索引，代表范围结束的索引。

## 返回值

此方法不返回值。

## 示例 1

本示例将范围的结尾设置为父节点的子节点。

本示例使用`setEnd()`方法设置范围的结束子节点。在这里，我们使用了`setStart()`方法来设置范围的起点，以完全组成一个范围。为了清楚定义范围，我们已经使用`toString()`方法将选定范围转换为文本。

### HTML

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        HTML DOM range setEnd() method
    </title>
</head>

<body>
    <h1>GeeksforGeeks</h1>

    <p id="exampleNode">
        Child 1<br>
        Child 2<br>
    </p>

    <script>
        const exampleNode = document
            .getElementById('exampleNode');

        const range = document.createRange();

        // 0th child gets at starting
        // of the range
        range.setStart(exampleNode, 0);

        // 3rd child gets at ending
        // of the range
        range.setEnd(exampleNode, 3);
        console.log(range);
        console.log(range.toString());
    </script>
</body>

</html>
```

**输出：** 在控制台中，可以看到创建的范围。

![](img/3d302f469fbfce9044732bda111f8727.png)

## 示例 2

本示例将范围的结尾设置为文本节点的字符。

### HTML

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        HTML DOM range setEnd() method
    </title>
</head>

<body>
    <h1>GeeksforGeeks</h1>

    <p id="exampleNode">
        Characters of this node will 
        be used to set the range.
    </p>

    <script>
        const exampleNode = document
            .getElementById('exampleNode');

        const textNode = exampleNode.childNodes[0];
        const range = document.createRange();

        // Starting of range will be 0th character
        range.setStart(textNode, 0);

        // Ending of range will be 54th character
        range.setEnd(textNode, 54);
        console.log(range);
        console.log(range.toString())
    </script>
</body>

</html>
```

**输出：** 在控制台中，可以看到创建的范围。

![](img/1ab274ffd316986e466eb2436c61d8f3.png)

## 支持的浏览器

*   Google Chrome
*   Edge
*   Firefox
*   Safari
*   Opera