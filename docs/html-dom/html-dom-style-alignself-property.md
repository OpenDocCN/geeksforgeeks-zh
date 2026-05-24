# HTML | DOM 样式对齐自身属性

> 原文:[https://www . geesforgeks . org/html-DOM-style-align self-property/](https://www.geeksforgeeks.org/html-dom-style-alignself-property/)

DOM Style**alignment self**属性用于**设置**或**返回**柔性容器内选定项目的对齐方式。

**语法:**

*   获取对齐自身属性

    ```html
    object.style.alignSelf
    ```

*   设置对齐自身属性

    ```html
    object.style.alignSelf = "auto | stretch | center | flex-start |
    flex-end | baseline | initial | inherit"
    ```

**属性值:**

*   **auto:** 元素继承父容器的“align-items”属性，如果没有父容器，则将其设置为“stretch”。这是默认样式。
*   **拉伸:**用于拉伸物品以适合容器。
*   **居中:**用于将容器中的物品居中。
*   **伸缩启动:**用于将物品定位在容器的开始位置
*   **弯曲端:**用于将物品定位在容器的末端。
*   **基线:**用于将物品定位在容器的基线。
*   **初始值:**用于将该属性设置为默认值。
*   **继承:**这将从其父级继承属性。

**返回值:**返回一个代表元素自身对齐属性的字符串值。

**示例-1:** 使用自动值。

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <title>DOM Style alignSelf Property
    </title>
    <style>
        .main {
            width: 200px;
            height: 150px;
            border: solid;
            display: flex;
            align-items: center;
        }

        #item {
            /* setting align-self to 
             flex-end to observe the
            effect of the auto value */
            align-self: flex-end;
        }
    </style>
</head>

<body>
    <h1 style="color: green">GeeksforGeeks
  </h1>

    <b>DOM Style alignSelf Property</b>
    <p>Click on the button to change the alignSelf 
    property to 'auto'</p>

    <div class="main">
        <div style="background-color:green;">
            GFG1 </div>
        <div style="background-color:white;">
            GFG2 </div>
        <div id="item" style="background-color:green;">
            GFG3 </div>
        <div style="background-color:white;">
            GFG4 </div>
    </div>

    <button onclick="changePos()">
        Change alignSelf property</button>

    <script>
        function changePos() {

            elem = document.querySelector('#item');

            // Setting alignSelf to auto
            elem.style.alignSelf = 'auto';
        }
    </script>
</body>

</html>
```

**输出:**

*   **点击按钮前:**
    ![](img/cd8e4cf0a7dfd0de698f0f5de7455b10.png)
*   **点击按钮后:**
    ![](img/4868f14159eabab79ef6d56da1ad37ce.png)

**示例-2:** 使用拉伸值。

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <title>DOM Style alignSelf Property
  </title>
    <style>
        .main {
            width: 200px;
            height: 150px;
            border: solid;
            display: flex;
            /* setting align-items to 
              center to observe the
            effect of the strench value */
            align-items: center;
        }
    </style>
</head>

<body>
    <h1 style="color: green">GeeksforGeeks</h1>
    <b>DOM Style alignSelf Property</b>
    <p>Click on the button to change the 
      alignSelf property to 'stretch'</p>

    <div class="main">
        <div style="background-color:green;">
          GFG1 </div>
        <div style="background-color:white;">
          GFG2 </div>
        <div id="item" 
             style="background-color:green;">
          GFG3 </div>
        <div style="background-color:white;">
          GFG4 </div>
    </div>
    <button onclick="changePos()">Change alignSelf property
  </button>

    <script>
        function changePos() {
            elem = document.querySelector('#item');

            // Setting alignSelf to stretch
            elem.style.alignSelf = 'stretch';
        }
    </script>
</body>

</html>
```

**输出:**

*   **点击按钮前:**
    ![](img/86e08f79adc7834e8422f03a14952770.png)
*   **点击按钮后:**
    ![](img/a9ece6a6f2448229c5c6eed72ccf483b.png)

**示例-3:** 使用中心值。

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <title>DOM Style alignSelf Property
  </title>
    <style>
        .main {
            width: 200px;
            height: 150px;
            border: solid;
            display: flex;
            /* setting align-items to 
            center to observe the
            effect of the center value */
            align-items: stretch;
        }
    </style>
</head>

<body>
    <h1 style="color: green">GeeksforGeeks
  </h1>
    <b>DOM Style alignSelf Property</b>
    <p>Click on the button to change the
      alignSelf property to 'center'</p>

    <div class="main">
        <div style="background-color:green;">
          GFG1 </div>
        <div style="background-color:white;">
          GFG2 </div>
        <div id="item" 
             style="background-color:green;">
          GFG3 </div>
        <div style="background-color:white;">
          GFG4 </div>
    </div>

    <button onclick="changePos()">
      Change alignSelf property</button>

    <script>
        function changePos() {
            elem = document.querySelector('#item');

            // Setting alignSelf to center
            elem.style.alignSelf = 'center';
        }
    </script>
</body>

</html>
```

**输出:**

*   **点击按钮前:**
    ![](img/8d56ebfaa5a4fe7b3e985041bee660a7.png)
*   **点击按钮后:**
    ![](img/52f0ebad47bfb9664f9eefd2c0e544e2.png)

**示例-4:** 使用弹性启动值。

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <title>DOM Style alignSelf Property
  </title>
    <style>
        .main {
            width: 200px;
            height: 150px;
            border: solid;
            display: flex;
        }
    </style>
</head>

<body>
    <h1 style="color: green">GeeksforGeeks
  </h1>
    <b>DOM Style alignSelf Property</b>
    <p>Click on the button to change the 
      alignSelf property to 'flex-start'</p>

    <div class="main">
        <div style="background-color:green;">
          GFG1 </div>
        <div style="background-color:white;">
          GFG2 </div>
        <div id="item" 
             style="background-color:green;">
          GFG3 </div>
        <div style="background-color:white;">
          GFG4 </div>
    </div>

    <button onclick="changePos()">
      Change alignSelf property</button>

    <script>
        function changePos() {
            elem = document.querySelector('#item');

            // Setting alignSelf to flex-start
            elem.style.alignSelf = 'flex-start';
        }
    </script>
</body>

</html>
```

**输出:**

*   **点击按钮前:**
    ![](img/ccddef9014e2c23230353c306012c440.png)
*   **点击按钮后:**
    ![](img/8af13ee2b82f342440d0582154f1f465.png)

**示例-5:** 使用弯曲端值。

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <title>DOM Style alignSelf Property
  </title>
    <style>
        .main {
            width: 200px;
            height: 150px;
            border: solid;
            display: flex;
        }
    </style>
</head>

<body>
    <h1 style="color: green">GeeksforGeeks
  </h1>
    <b>DOM Style alignSelf Property</b>
    <p>Click on the button to change the 
      alignSelf property to 'flex-end'</p>

    <div class="main">
        <div style="background-color:green;">
          GFG1 </div>
        <div style="background-color:white;">
          GFG2 </div>
        <div id="item" 
             style="background-color:green;">
          GFG3 </div>
        <div style="background-color:white;">
          GFG4 </div>
    </div>

    <button onclick="changePos()">
      Change alignSelf property</button>

    <script>
        function changePos() {
            elem = document.querySelector('#item');

            // Setting alignSelf to flex-end
            elem.style.alignSelf = 'flex-end';
        }
    </script>
</body>

</html>
```

**输出:**

*   **点击按钮前:**
    ![](img/d4eb439ea98720322ec8fdb7741b0929.png)
*   **点击按钮后:**
    ![](img/03f8e966cc59ddbe3e0db8f4d5de1a1a.png)

**示例-6:** 使用基线值。

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <title>DOM Style alignSelf Property</title>
    <style>
        .main {
            width: 200px;
            height: 150px;
            border: solid;
            display: flex;
        }
    </style>
</head>

<body>
    <h1 style="color: green">GeeksforGeeks
  </h1>
    <b>DOM Style alignSelf Property</b>
    <p>Click on the button to change the 
      alignSelf property to 'baseline'</p>

    <div class="main">
        <div style="background-color:green;"> 
          GFG1 </div>
        <div style="background-color:white;">
          GFG2 </div>
        <div id="item"
             style="background-color:green;">
          GFG3 </div>
        <div style="background-color:white;">
          GFG4 </div>
    </div>

    <button onclick="changePos()">
      Change alignSelf property</button>

    <script>
        function changePos() {
            elem = document.querySelector('#item');

            // Setting alignSelf to baseline
            elem.style.alignSelf = 'baseline';
        }
    </script>
</body>

</html>
```

**输出:**

*   **点击按钮前:**
    ![](img/0e68823eaec0fb9672a057ef6606f8cb.png)
*   **点击按钮后:**
    ![](img/f613da7fbe9cd8efcaf31f7ff7823499.png)

**示例-7:** 使用初始值。

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <title>DOM Style alignSelf Property
  </title>
    <style>
        .main {
            width: 200px;
            height: 150px;
            border: solid;
            display: flex;
            align-items: center;
        }

        #item {
            /* setting align-self to 
             flex-end to observe the
            effect of the initial value */
            align-self: flex-end;
        }
    </style>
</head>

<body>
    <h1 style="color: green">GeeksforGeeks
  </h1>
    <b>DOM Style alignSelf Property</b>
    <p>Click on the button to change the 
      alignSelf property to 'initial'</p>

    <div class="main">
        <div style="background-color:green;"> 
          GFG1 </div>
        <div style="background-color:white;">
          GFG2 </div>
        <div id="item" 
             style="background-color:green;">
          GFG3 </div>
        <div style="background-color:white;">
          GFG4 </div>
    </div>
    <button onclick="changePos()">
      Change alignSelf property</button>

    <script>
        function changePos() {
            elem = document.querySelector('#item');

            // Setting alignSelf to initial
            elem.style.alignSelf = 'initial';
        }
    </script>
</body>

</html>
```

**输出:**

*   **点击按钮前:**
    ![](img/9c9ad745fffbe7f262f5e104b4e871cd.png)
*   **点击按钮后:**
    ![](img/9368a40f5420f386b361dcaa88978b5a.png)

**示例-8:** 使用继承值。

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <title>DOM Style alignSelf Property
  </title>
    <style>
        .main {
            width: 200px;
            height: 150px;
            border: solid;
            display: flex;
            /* this itself is the
          parent of the item */
            align-items: center;
        }

        #item {
            /* setting align-self to 
          flex-end to observe the
            effect of the inherit value */
            align-self: flex-end;
        }
    </style>
</head>

<body>
    <h1 style="color: green">GeeksforGeeks
  </h1>
    <b>DOM Style alignSelf Property</b>
    <p>Click on the button to change the
      alignSelf property to 'inherit'</p>

    <div id="parent">
        <div class="main">
            <div style="background-color:green;">
              GFG1 </div>
            <div style="background-color:white;"> 
              GFG2 </div>
            <div id="item" 
                 style="background-color:green;">
              GFG3 </div>
            <div style="background-color:white;">
              GFG4 </div>
        </div>
    </div>

    <button onclick="changePos()">
      Change alignSelf property</button>

    <script>
        function changePos() {
            elem = document.querySelector('#item');

            // Setting alignSelf to inherit
            elem.style.alignSelf = 'inherit';
        }
    </script>
</body>

</html>
```

**输出:**

*   **点击按钮前:**
    ![](img/58892aaadcfbd561de88b55656766a3a.png)
*   **点击按钮后:**
    ![](img/44d0e98dcaf79d19d4e7723b342ebf8e.png)

**支持的浏览器:**由 *alignSelf* 属性支持的浏览器如下:

*   谷歌 Chrome 21.0
*   Internet Explorer 11.0
*   Firefox 20.0
*   歌剧 12.1
*   Safari 7.0