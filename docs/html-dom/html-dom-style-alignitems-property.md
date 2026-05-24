# HTML | DOM 样式对齐属性

> 原文:[https://www . geesforgeks . org/html-DOM-style-alignitems-property/](https://www.geeksforgeeks.org/html-dom-style-alignitems-property/)

DOM Style **alignItems** 属性用于设置或返回灵活容器中项目的默认对齐方式。

**语法:**

*   获得 alignItems 属性

    ```html
    object.style.alignItems
    ```

*   设置对齐属性

    ```html
    object.style.alignItems = "stretch|center|flex-start|flex-end|
    baseline|initial|inherit"

    ```

**属性值:**

*   **拉伸:**用于拉伸物品以适应容器。这是默认值。
*   **居中:**用于将容器中的物品居中。
*   **flex-start:** 这用于将项目定位在容器的开头。
*   **弯曲端:**用于将物品放置在容器的末端。
*   **基线:**用于将物品定位在集装箱的基线上。
*   **初始值:**用于将该属性设置为默认值。
*   **继承:**这将从其父级继承属性。

**返回值:**返回一个字符串值，代表元素的 align-items 属性。

使用以下示例解释这些值:

**示例-1:** 使用拉伸值。

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <title>DOM Style alignItems Property</title>
    <style>
        .main {
            width: 200px;
            height: 150px;
            border: solid;
            display: flex;

            /* setting align-items to center to observe the
            effect of the stretch value */
            align-items: center;
        }
    </style>
</head>

<body>
    <h1 style="color: green">GeeksforGeeks</h1>
    <b>DOM Style alignItems Property</b>
    <p>Click on the button to change the 
       alignItems property to 'stretch'</p>

    <div class="main">
        <div style="background-color:lightblue;"> 
          Item 1 </div>
        <div style="background-color:lightgreen;"> 
          Item 2 </div>
        <div style="background-color:lightsalmon;"> 
          Item 3 </div>
        <div style="background-color:lightyellow;"> 
          Item 4 </div>
    </div>

    <button onclick="changePos()">
      Change alignItems property
    </button>

    <script>
        function changePos() {
            elem = document.querySelector('.main');

            // Setting alignItems to stretch
            elem.style.alignItems = 'stretch';
        }
    </script>
</body>

</html>
```

**输出:**

*   **按下按钮前:**
    ![](img/64444e3e15146699c819ee4900070fad.png)
*   **按下按钮后:**
    ![](img/de32ea93daa7babd48015e13813e4d2f.png)

**示例-2:** 使用中心值。

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <title>DOM Style alignItems Property</title>
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
    <h1 style="color: green">GeeksforGeeks</h1>
    <b>DOM Style alignItems Property</b>
    <p>Click on the button to change the 
        alignItems property to 'center'</p>

    <div class="main">
        <div style="background-color:lightblue;"> 
          Item 1 </div>
        <div style="background-color:lightgreen;"> 
          Item 2 </div>
        <div style="background-color:lightsalmon;"> 
          Item 3 </div>
        <div style="background-color:lightyellow;"> 
          Item 4 </div>
    </div>

    <button onclick="changePos()">
      Change alignItems property
    </button>

    <script>
        function changePos() {
            elem = document.querySelector('.main');

            // Setting alignItems to center
            elem.style.alignItems = 'center';
        }
    </script>
</body>

</html>
```

**输出:**

*   **按下按钮前:**
    ![](img/f15878f8553051bf2e760a6ac5ded1f9.png)
*   **按下按钮后:**
    ![](img/6b28a18d95474ec094e737dff197f519.png)

**示例-3:** 使用弹性启动值。

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <title>DOM Style alignItems Property</title>
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
    <h1 style="color: green">GeeksforGeeks</h1>
    <b>DOM Style alignItems Property</b>
    <p>Click on the button to change the 
       alignItems property to 'flex-start'</p>

    <div class="main">
        <div style="background-color:lightblue;"> 
          Item 1 </div>
        <div style="background-color:lightgreen;"> 
          Item 2 </div>
        <div style="background-color:lightsalmon;"> 
          Item 3 </div>
        <div style="background-color:lightyellow;"> 
          Item 4 </div>
    </div>

    <button onclick="changePos()">
      Change alignItems property
    </button>

    <script>
        function changePos() {
            elem = document.querySelector('.main');

            // Setting alignItems to flex-start
            elem.style.alignItems = 'flex-start';
        }
    </script>
</body>

</html>
```

**输出:**

*   **按下按钮前:**
    ![flex-start-before](img/d503f7651305bd2e49f1de08fca629bb.png)
*   **按下按钮后:**
    ![](img/7aec824bc60a7002907e3fa184b5a2d3.png)

**示例-4:** 使用弯曲端值。

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <title>DOM Style alignItems Property</title>
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
    <h1 style="color: green">GeeksforGeeks</h1>
    <b>DOM Style alignItems Property</b>
    <p>Click on the button to change the 
       alignItems property to 'flex-end'</p>

    <div class="main">
        <div style="background-color:lightblue;"> 
          Item 1 </div>
        <div style="background-color:lightgreen;"> 
          Item 2 </div>
        <div style="background-color:lightsalmon;"> 
          Item 3 </div>
        <div style="background-color:lightyellow;"> 
          Item 4 </div>
    </div>

    <button onclick="changePos()">
      Change alignItems property
    </button>

    <script>
        function changePos() {
            elem = document.querySelector('.main');

            // Setting alignItems to flex-end
            elem.style.alignItems = 'flex-end';
        }
    </script>
</body>

</html>
```

**输出:**

*   **按下按钮前:**
    ![flex-end-before](img/46a22c37fc32a093650b722eea72f2e1.png)
*   **按下按钮后:**
    ![](img/7ffe4fcec46a2da4dcebdab8319b36da.png)

**示例-5:** 使用基线值。

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <title>DOM Style alignItems Property</title>
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
    <h1 style="color: green">GeeksforGeeks</h1>
    <b>DOM Style alignItems Property</b>
    <p>Click on the button to change the 
      alignItems property to 'baseline'</p>

    <div class="main">
        <div style="background-color:lightblue;">
          Item 1 </div>
        <div style="background-color:lightgreen;">
          Item 2 </div>
        <div style="background-color:lightsalmon;">
          Item 3 </div>
        <div style="background-color:lightyellow;">
          Item 4 </div>
    </div>

    <button onclick="changePos()">
      Change alignItems property
    </button>

    <script>
        function changePos() {
            elem = document.querySelector('.main');

            // Setting alignItems to baseline
            elem.style.alignItems = 'baseline';
        }
    </script>
</body>

</html>
```

**输出:**

*   **按下按钮前:**
    ![baseline-before](img/9e90ca37be59f89e7a05edf6ce8228ed.png)
*   **按下按钮后:**
    ![](img/0f63f426dbcb251000027785aa179b11.png)

**示例-6:** 使用初始值。这会将属性设置为默认值。

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <title>DOM Style alignItems Property</title>
    <style>
        .main {
            width: 200px;
            height: 150px;
            border: solid;
            display: flex;
            /* setting align-items to center 
             to observe the effect of the 
             initial value */
            align-items: center;
        }
    </style>
</head>

<body>
    <h1 style="color: green">GeeksforGeeks</h1>
    <b>DOM Style alignItems Property</b>
    <p>Click on the button to change the 
      alignItems property to 'initial'</p>

    <div class="main">
        <div style="background-color:lightblue;"> 
          Item 1 </div>
        <div style="background-color:lightgreen;"> 
          Item 2 </div>
        <div style="background-color:lightsalmon;"> 
          Item 3 </div>
        <div style="background-color:lightyellow;"> 
          Item 4 </div>
    </div>

    <button onclick="changePos()">
      Change alignItems property
    </button>

    <script>
        function changePos() {
            elem = document.querySelector('.main');

            // Setting alignItems to initial
            elem.style.alignItems = 'initial';
        }
    </script>
</body>

</html>
```

**输出:**

*   **按下按钮前:**
    ![](img/7f8a6f5486fd4c77129fbcfa2c89fe8f.png)
*   **按下按钮后:**
    ![](img/54e3c4163f86c5aa3772cfa59df302f4.png)

**示例-7:** 使用继承值。这将从其父元素继承位置。

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <title>DOM Style alignItems Property</title>
    <style>
        .main {
            width: 200px;
            height: 150px;
            border: solid;
            display: flex;
        }

        #parent {
            /* Setting the parent div's 
              align-items to flex-end */
            align-items: flex-end;
        }
    </style>
</head>

<body>
    <h1 style="color: green">GeeksforGeeks</h1>
    <b>DOM Style alignItems Property</b>
    <p>Click on the button to change the 
       alignItems property to 'inherit'</p>

    <div id="parent">
        <div class="main">
            <div style="background-color:lightblue;"> 
              Item 1 </div>
            <div style="background-color:lightgreen;"> 
              Item 2 </div>
            <div style="background-color:lightsalmon;"> 
              Item 3 </div>
            <div style="background-color:lightyellow;"> 
              Item 4 </div>
        </div>
    </div>

    <button onclick="changePos()">
      Change alignItems property
    </button>

    <script>
        function changePos() {
            elem = document.querySelector('.main');

            // Setting alignItems to inherit from parent div
            elem.style.alignItems = 'inherit';
        }
    </script>
</body>

</html>
```

**输出:**

*   **按下按钮前:**
    ![inherit-before](img/08be376505b6f1f8a81004e2096d1970.png)
*   **按下按钮后:**
    ![](img/31dab12d7d0841a9c837e5d2d9cbac5e.png)

**支持的浏览器:***alignItems Property*支持的浏览器如下:

*   铬 21.0
*   Internet Explorer 11.0
*   Firefox 20.0
*   歌剧 12.1
*   Safari 7.0