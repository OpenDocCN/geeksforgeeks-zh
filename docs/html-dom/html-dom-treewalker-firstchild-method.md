# HTML DOM TreeWalker firstChild()方法

> 原文:[https://www . geesforgeks . org/html-DOM-tree walker-first child-method/](https://www.geeksforgeeks.org/html-dom-treewalker-firstchild-method/)

**TreeWalker firstChild()** 方法将当前节点移动到当前节点的**第一个可见子节点，并返回**第一个找到的子节点**。如果文档中不存在这样的子级，则此方法返回 null。**

**语法:**

```html
node = treeWalker.firstChild();
```

**参数:**该方法不取参数。

**返回值:**

*   如果存在，返回节点的**第一个子节点**。
*   如果不存在这样的子代，则返回 **null** 。

**示例:**在本例中，创建一个 TreeWalker，并因此显示了 TreeWalker 节点的第一个子节点。

```html
<!doctype html>
<html>
<head>
    <meta charset="utf-8">
<title>HTML DOM TreeWalker firstChild() method</title>    
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
            var node = treeWalker.firstChild();
            console.log(node) 
        }
</script>
</html>
```

**输出:**

**按钮点击前:**

![](img/eb973973982016f69868389566de333c.png)

**按钮点击后:**

![](img/5da0ad3b872dbb62b827a7a4c20439bf.png)

**支持的浏览器:**

*   谷歌 Chrome
*   边缘
*   火狐浏览器
*   旅行队
*   歌剧
*   微软公司出品的 web 浏览器