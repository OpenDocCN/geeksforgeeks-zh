# HTML DOM TreeWalker lastChild()方法

> 原文:[https://www . geesforgeks . org/html-DOM-tree walker-last child-method/](https://www.geeksforgeeks.org/html-dom-treewalker-lastchild-method/)

**TreeWalker lastChild()** 方法将当前节点移动到当前节点的**最后一个可见子节点**，并返回**最后找到的子节点**。如果文档中不存在这样的子级，则此方法返回 null。

**语法:**

```html
node = treeWalker.lastChild();

```

**参数:**该方法不取参数。

**返回值:**

*   如果存在，返回节点的**最后一个子节点**。
*   如果不存在这样的子代，则返回 **null** 。

**示例:**在本例中，创建一个带有头节点的 TreeWalker，因此显示了该 TreeWalker 节点的最后一个子节点。

```html
<!doctype html>
<html>
<head>
    <meta charset="utf-8">
<title>HTML DOM TreeWalker lastChild() method</title>    
</head>
<body>
    <h1>GeeksforGeeks</h1>
    <p>Click Below</p>
    <button onclick="get()">Click</button>
</body>
<script>
        var treeWalker = document.createTreeWalker(
        document.head,
        NodeFilter.SHOW_ELEMENT,
        { acceptNode: function(node) {
 return NodeFilter.FILTER_ACCEPT; } },
        false
);
        function get(){
            var node = treeWalker.lastChild();
            console.log(node) 
        }
</script>
</html>
```

**输出:**

**按钮点击前:**

![](img/eb973973982016f69868389566de333c.png)

**按钮点击后:**在控制台中，可以看到树行者节点的最后一个子节点，即 **<标题>** 。

![](img/15817c8fea8b4247e22e8ff62e38e403.png)

**支持的浏览器:**

*   谷歌 Chrome
*   边缘
*   火狐浏览器
*   旅行队
*   歌剧
*   微软公司出品的 web 浏览器