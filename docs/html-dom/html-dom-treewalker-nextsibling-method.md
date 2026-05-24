# HTML DOM treevolker next sibling()方法

> 原文:[https://www . geesforgeks . org/html-DOM-tree walker-next sibling-method/](https://www.geeksforgeeks.org/html-dom-treewalker-nextsibling-method/)

**TreeWalker nextSibling()** 方法将当前节点移动到它的**下一个兄弟节点**，如果有的话，并返回**找到的兄弟节点**。如果文档中不存在这样的子代，则该方法返回 **null** 。

**语法:**

```html
node = treeWalker.nextSibling();

```

**参数:**该方法不取参数。

**返回值:**

*   如果存在，返回当前节点的下一个可见同级。
*   如果不存在这样的子代，则返回 **null** 。

**示例:**在本例中，我创建了一个具有**主体**节点的树行者，因此显示了该树行者第一个节点的下一个可见兄弟节点。

```html
<!doctype html>
<html>
<head>
    <meta charset="utf-8">
<title>HTML DOM TreeWalker nextSibling() method</title>    
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
            var node = treeWalker.nextSibling();
            console.log(node) 
        }
</script>
</html>
```

**输出:**

**按钮点击前:**

![](img/eb973973982016f69868389566de333c.png)

**按钮点击后:**在控制台中，可以看到树行者节点的身体第一个元素的下一个可见同级，即< p >标签。

![](img/4b060f246ce9b6f4d6c7ea9d4f183f91.png)

**支持的浏览器:**

*   谷歌 Chrome
*   边缘
*   火狐浏览器
*   旅行队
*   歌剧
*   微软公司出品的 web 浏览器