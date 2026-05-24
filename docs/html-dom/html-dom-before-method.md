# HTML | DOM before()方法

> 原文:[https://www.geeksforgeeks.org/html-dom-before-method/](https://www.geeksforgeeks.org/html-dom-before-method/)

方法用于在**子节点的**父节点的子列表中插入一组**节点对象**或 **HTML DOMString** 对象。元素被插入到我们提到的子节点**之前。**

**语法:**

```html
ChildNode.before(Node or DOMString)
```

**参数:**该方法接受如上所述的单个参数，描述如下:

*   **节点:**它是一组**节点**对象或 **HTML DOMString** 对象，必须插入到子节点之前。

**示例 1:** 在本例中，我们将在子元素之前向 DOM 插入一个元素节点。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        HTML | DOM before() method
    </title>
</head>

<body>
    <div id="div">
        <h1>GeeksforGeeks</h1>
        <p id="p">Child Node</p>
    </div>

    <button onclick="add()">
        click to add
    </button>

    <script>
        // Get the parent element
        var parent = document.getElementById("div");
        console.log(parent)

        // Get the element to add before
        var para = document.getElementById("p");

        // Function to add the element
        function add() {

            // Create a new element to add
            const div = document.createElement("div");
            div.innerHTML = "<h4>new node</h4>";

            // Insert the created element
            para.before(div);
        }
        console.log(parent.outerHTML);
    </script>
</body>

</html>
```

**输出:**

在输出中，可以看到点击按钮后，在子< p >元素前插入了一个**新节点。**

*   **点击按钮前:**

    ![](img/3a9d8f885d547ce156e3e1236540e671.png)

*   **点击按钮后:**

    ![](img/d5255ff0bcc37916a824c42e291a9f33.png)

**示例 2:** 在本例中，我们将在子节点之前插入一些文本。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        HTML | DOM before() method
    </title>
</head>

<body>
    <div id="div">
        <h1>GeeksforGeeks</h1>
        <p id="p">Child Node</p>
    </div>

    <button onclick="add()">
        click to add
    </button>

    <script>
        // Get the parent element
        var parent = document.getElementById("div");
        console.log(parent)

        // Get the element to add before
        var para = document.getElementById("p");

        // Function to add the element
        function add() {

            // Insert a text element
            // before this element
            para.before(
                "Text Added Before ChildNode");
        }
        console.log(parent.outerHTML);
    </script>
</body>

</html>
```

**输出:**

*   **点击按钮前:**

    ![](img/3a9d8f885d547ce156e3e1236540e671.png)

*   **点击按钮后:**

    ![](img/91d7fb105b57c217611e8ad1b8db8293.png)

**支持的浏览器:**方法之前的 **DOM 支持的浏览器如下:**

*   谷歌 Chrome
*   边缘
*   火狐浏览器
*   歌剧