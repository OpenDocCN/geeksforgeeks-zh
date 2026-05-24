# HTML | DOM ParentNode.prepend()方法

> 原文:[https://www . geesforgeks . org/html-DOM-parent node-prepend-method/](https://www.geeksforgeeks.org/html-dom-parentnode-prepend-method/)

方法在父节点的第一个子节点之前插入一组节点对象或多字符串对象。因此，子节点被设置为节点对象列表的第 0 个<sup>索引。</sup>

**语法:**

```html
ParentNode.prepend( ChildNodesToPrepend );
```

**参数:**

*   **ChildNodesToPrepend:** 要前置的子节点充当此方法的参数。
*   **前置文字:**我们也可以前置文字。

**返回值:**该方法返回**未定义。**

以下示例说明了 ParentNode.prepend()方法:

**示例 1:** 前置元素。为了展示这个方法，我们创建了三个元素**父节点，子节点 1 和子节点 2。**然后我们将子节点 1 和子节点 2 前置到父节点。

在控制台中，我们显示了父节点的子节点。

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <title>Prepend</title>
</head>

<body>
    <h1>GeeksforGeeks</h1>

    <script>
        var parentNode = document.createElement("div");
        var Child1 = document.createElement("p");
        var Child2 = document.createElement("div");
        parentNode.prepend(Child1);
        parentNode.prepend(Child2);
        console.log(parentNode.childNodes);
    </script>
</body>

</html>
```

**输出:**

在控制台中，您可以看到父节点的子节点列表。一个是 **div** 一个是 **p**

![](img/7645171f5f2487232b557ab5c7704517.png)

**例 2:** 前置文本。在这个例子中，我们在元素的内部 HTML 和元素的文本内容前添加了一些文本。

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <title>Prepend</title>
</head>

<body>
    <h1>GeeksforGeeks</h1>

    <script>
        var parent = document.createElement("div");
        parent.innerHTML = 
            "A Computer Science Portal for Geeks";
        parent.prepend("GeeksforGeeks : ");
        console.log(parent.textContent);
    </script>
</body>

</html>
```

**输出:**

在控制台中，可以看到**父**元素的文本内容。

![](img/f66d456b44c4ec281a04e70d898760ce.png)