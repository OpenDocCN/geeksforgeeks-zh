# JavaScript 中 DOM parentNode 和 parentElement 的区别

> 原文: [https://www.geeksforgeeks.org/difference-between-dom-parentnode-and-parentelement-in-javascript/](https://www.geeksforgeeks.org/difference-between-dom-parentnode-and-parentelement-in-javascript/)

## parentNode

`parentNode` 是只读属性，它返回所选节点的父节点作为节点对象。节点对象代表文档树中的单个节点，节点可以是元素节点、文本节点等。

**语法:**

```javascript
node.parentNode
```

**返回值:** 父节点属性返回父节点对象（如果存在），否则将返回 `null`。

**示例:**

```html
<!DOCTYPE html>
<html>
<body>
    <!--setting styles for our document-->
    <style>
        p {
            color: green;
        }
    </style>

    <p>GeeksForGeeks</p>

    <div>
        <p id="gfg">Click the button to get the node name of the parent node.</p>
        <!--here 'p' element is inside 'div' element meaning that 'div' is the parent of 'p' element here-->
    </div>

    <button onclick="myParentNode()">Try it</button>

    <p id="text"></p>

    <script>
        function myParentNode() {
            var geek = document.getElementById("gfg").parentNode.nodeName;
            /*appending parent node to the 'p' element with id named text*/
            document.getElementById("text").innerHTML = geek;
        }
    </script>
</body>
</html>
```

**输出:**
![](img/730e69edcbef8b37961235be20f8f5ab.png)

## parentElement

`parentElement` 是只读属性，它返回所选元素的父元素。元素对象代表一个 HTML 元素，如 `P`、`DIV` 等。

**语法:**

```javascript
node.parentElement
```

**返回值:** `parentElement` 属性返回表示父元素的元素对象（如果存在），否则将返回 `null`。

**示例:**

```html
<!DOCTYPE html>
<html>
<body>
    <!--setting styles for our document-->
    <style>
        p,
        ol {
            color: green;
        }
    </style>

    <p>GeeksForGeeks Courses</p>

    <ol>
        <li id="geek">DSA</li>
        <li>Interview Preparation</li>
        <li>Geeks Classes</li>
    </ol>

    <p>Click the button to get the node name of the parent element</p>

    <button onclick="myParentElement()">
        Click to know the parent element
    </button>
    <!--here 'li' element is inside 'ol' element meaning that 'ol' is the parent of 'li' element here-->
    <p id="gfg"></p>

    <script>
        function myParentElement() {
            var text = document.getElementById("geek").parentElement.nodeName;
            document.getElementById("gfg").innerHTML = text;
        }
    </script>
</body>
</html>
```

**输出:**
![](img/ec4423b1224e8cb863efa000adc5a9a7.png)

## 区别

如果父元素不是元素节点，那么 `parentElement` 返回 `null`，这就是 `parentElement` 和 `parentNode` 的主要区别。在许多情况下，人们可以使用它们中的任何一个，在大多数情况下，它们是相同的。例如:

```javascript
// returns the document node
document.documentElement.parentNode;

// returns null
document.documentElement.parentElement;
```

HTML 元素 (`document.documentElement`) 没有作为元素的父元素，它是一个节点，因此，父元素为空。

## 支持的浏览器

以下列出了 `parentNode` 和 `parentElement` 属性支持的浏览器:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   苹果 Safari
*   歌剧