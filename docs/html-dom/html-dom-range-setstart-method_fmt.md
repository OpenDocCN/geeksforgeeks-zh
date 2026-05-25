# HTML DOM Range setStart() 方法

> 原文：[https://www.geeksforgeeks.org/html-dom-range-setstart-method/](https://www.geeksforgeeks.org/html-dom-range-setstart-method/)

`setStart()` 方法用于设置 `Range` 的开始位置。`startNode` 可以用作文本节点、子节点等。`startOffset` 可以是从 `startNode` 开始的字符数，也可以是 `startNode` 开始之间的子节点数。

**语法：**

```html
range.setStart(startNode, startOffset);
```

**参数：**

*   `startNode`：用于开始范围的节点。
*   `startOffset`：此参数是大于或等于零的 `offsetIndex`，表示从起始节点开始的范围的索引。

**返回值：** 此方法不返回值。

**例 1：** 在本例中，设置父节点的范围子节点的起点。

本示例使用 `setStart()` 方法设置范围的起始子节点。在这里，我们使用了 `setEnd()` 方法来设置范围的结束。为了清楚定义范围，我们已经使用 `toString()` 方法将选定范围转换为文本。

## HTML

```html
<!DOCTYPE html>
<html>

<body>
    <h1>GeeksforGeeks</h1>
    <p id="parent">
        Child 1<br>
        Child 2<br>
    </p>

<script>
        const example = document
            .getElementById('parent');

        const range = document.createRange();
        range.setStart(example, 0);
        range.setEnd(example, 3);
        console.log(range);
        console.log(range.toString());
    </script>
</body>

</html>
```

**输出：** 在控制台中，可以看到创建的范围。

![](img/3d302f469fbfce9044732bda111f8727.png)

**例 2：** 在本例中，通过获取文本节点的字符来设置范围的开始。

## HTML

```html
<!DOCTYPE html>
<html>

<body>
    <h1>GeeksforGeeks</h1>

    <p id="example">
        Characters of this node will
        be used to set the range.
    </p>

<script>
        const example = document
            .getElementById('example');

        const textNode = example.childNodes[0];
        const range = document.createRange();

        // Starting of range will 
        // be 0th character
        range.setStart(textNode, 0);

        // Ending of range will be 
        // 54th character
        range.setEnd(textNode, 54);
        console.log(range);
        console.log(range.toString())
    </script>
</body>

</html>
```

**输出：** 在控制台中，可以看到创建的范围。

![](img/1ab274ffd316986e466eb2436c61d8f3.png)

**支持的浏览器：**

*   Google Chrome
*   Edge
*   Firefox
*   Safari
*   Opera