# HTML | DOM 样式边框开始属性

> 原文:[https://www . geeksforgeeks . org/html-DOM-style-borderimagebegin-property/](https://www.geeksforgeeks.org/html-dom-style-borderimageoutset-property/)

在样式**边框开始**包含边框的空间中，要绘制的图像称为边框图像空间。默认情况下，边框图像区域的边界与元素边框的边界相匹配。但是，可以使用 border-image-begin 属性扩展这些边界。
border-image-begin 属性指定边框图像空间从元素的边框区域延伸的距离。这个量被描述为一组起始值，这些值指定了边框图像空间从顶部、右侧、底部和左侧边缘扩展的量。
**语法:**

*   它返回 borderImageOutset 属性

```html
object.style.borderImageOutset
```

*   它用于设置 borderImageOutset 属性

```html
object.style.borderImageOutset="length | number | initial | inherit"
```

**返回值:**返回边框图像区域超出边框框的量。

**属性值**

*   **语法:**

```html
borderImageOutset = "10px"
```

*   **Example:**

    ## Hypertext Markup Language

```html
<!DOCTYPE html>
<html>

<head>
    <style>
        #GFG {
            width: 200px;
            height: 150px;
            margin-left: 180px;
            font-size: 20px;
            background-color: lightgrey;
            border: 20px solid transparent;
            border-image: 
url('https://media.geeksforgeeks.org/wp-content/uploads/bir1.png') 
              50 50 stretch;
            border-image-outset: 5px;
        }
    </style>
</head>

<body align="center">
    <button onclick="myGeeks()">Click it</button>

<p>On click, border-image-outset property changes.</p>

    <div id="GFG">
        <p align="center">
            GeeksforGeeks
        </p>

    </div>
    <script>
        function myGeeks() {
            document.getElementById("GFG")
                .style.borderImageOutset = "10px";
        }
    </script>
</body>

</html>                
```