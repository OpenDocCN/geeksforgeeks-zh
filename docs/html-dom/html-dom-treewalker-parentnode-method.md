# HTML DOM TreeWalker parentNode()方法

> 原文:[https://www . geesforgeks . org/html-DOM-tree walker-parent node-method/](https://www.geeksforgeeks.org/html-dom-treewalker-parentnode-method/)

**TreeWalker parentNode()** 方法将当前节点移动到文档顺序中**第一个可见的祖先节点或 TreeWalker** 的父节点，并返回找到的节点。如果文档中不存在这样的子级，则此方法返回 null。

**语法:**

```html
node = treeWalker.parentNode();

```

**参数:**该方法不取参数。

**返回值:**

*   如果存在，返回树行者的**父节点**。
*   如果不存在这样的子代，则返回 **null** 。

**示例:**在本例中，创建一个带有**主体**节点的树行者，并显示该树行者第一个节点的父节点。

```html
<!doctype html>
<html>
<head>
    <meta charset="utf-8">
<title>HTML DOM TreeWalker parentNode() method</title>    
</head>
<body>
    <h1>GeeksforGeeks</h1>
    <p>Click Below</p>
    <button onclick="get()">Click</button>
</body>
<script>
        var treeWalker = document.createTreeWalker(
        document.body,
        NodeFilter.SHOW_ELEMENT,
        { acceptNode: function(node) { 
return NodeFilter.FILTER_ACCEPT; } },
        false
);
        function get(){
            treeWalker.firstChild();
            var node = treeWalker.parentNode();
            console.log(node);
        }
</script>
</html>
```

**输出:**

**按钮点击前:**

![](img/eb973973982016f69868389566de333c.png)

**按钮点击后:**在控制台中，可以看到树行者的父节点，即<体>标签。

![](img/d126fb219c0e89af7570de8444c972c1.png)

**支持的浏览器:**

*   谷歌 Chrome
*   边缘
*   火狐浏览器
*   旅行队
*   歌剧
*   微软公司出品的 web 浏览器