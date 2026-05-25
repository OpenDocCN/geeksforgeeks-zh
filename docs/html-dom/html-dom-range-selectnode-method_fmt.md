# HTML DOM Range selectNode() 方法

> 原文：[https://www.geeksforgeeks.org/html-dom-range-selectnode-method/](https://www.geeksforgeeks.org/html-dom-range-selectnode-method/)

`selectNode()` 方法将 `Range` 的内容设置为包含一个节点。范围的开始和结束将与 `referenceNode` 相同。

## 语法

```html
range.selectNode(referenceNode);
```

## 参数

*   `referenceNode`：用于设置范围内容的节点。

## 返回值

此方法没有返回值。

## 示例

本示例展示了如何使用该方法设置范围的内容。

为了更好地说明，控制台通过 `toString()` 方法在字符串文本中记录了新的范围内容。

### HTML

```html
<html>
<head>
<title>HTML DOM range selectNode() method</title>   
</head>
<body>
    <h1>GeeksforGeeks</h1>

<p>This is the Range Content</p>

</body>
<script>
    let range = document.createRange();
    let referenceNode = document.getElementsByTagName('p').item(0);
    range.selectNode(referenceNode);
    console.log(range);
    console.log(range.toString());
</script>
</html>
```

## 输出

在控制台，可以看到范围内容。

![](img/af7084be1fdde14b6c7039531b6a2c53.png)

## 支持的浏览器

*   Google Chrome
*   Edge
*   Firefox
*   Safari
*   Opera
*   Internet Explorer