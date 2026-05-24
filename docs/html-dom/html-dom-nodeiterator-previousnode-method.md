# HTML DOM 节点迭代器 previousNode()方法

> 原文:[https://www . geesforgeks . org/html-DOM-node iterator-previousnode-method/](https://www.geeksforgeeks.org/html-dom-nodeiterator-previousnode-method/)

**NodeIterator . previousnode()**方法将 NodeIterator 设置为文档中的上一个节点，并返回上一个节点。当集合中没有剩余节点时，该方法返回**空值**。

**语法:**

```html
node = nodeIterator.previousNode();
```

**参数:**该方法不取参数。

**返回值:**该方法返回集合中的上一个节点。

**示例:**在本例中，我们将创建一个节点迭代器，因此将使用 previousNode()方法向后迭代。

```html
<!DOCTYPE HTML> 
<html>  
<head>
    <meta charset="UTF-8">
    <title>HTML | DOM previousNode() Method</title>
</head>   

<body style="text-align:center;">
    <h1 style="color:green;">  
     GeeksforGeeks
    </h1> 
    <p> 
HTML | DOM previousNode() Method
    </p>

    <button onclick = "Geeks()">
    Click Here
    </button>
    <p id="a"></p>
    <script> 
        var a = document.getElementById("a");
        function Geeks(){
           const nodeIterator = document.createNodeIterator(
                document.body,
                NodeFilter.SHOW_ELEMENT
                )

            let nextNode=nodeIterator.nextNode();
            nextNode=nodeIterator.nextNode();
            var prevNode=nodeIterator.previousNode();
            a.innerHTML =
'Previous Node content is : '+prevNode.textContent;
            console.log(prevNode);
}
</script>
</body>
</html>
```

**输出:**

**点击按钮前:**

![](img/d05ec9c8b547f00620eae7b7d0172ce2.png)

**点击按钮后:**

![](img/4f510839df0a163044220ed7bbe44c7d.png)

控制台中的**:控制台中的**，可以看到上一个节点。

![](img/57ad0791d1487ac5ec515e03c89480c6.png)

**支持的浏览器:**

*   谷歌 Chrome
*   边缘
*   火狐浏览器
*   旅行队
*   歌剧
*   微软公司出品的 web 浏览器