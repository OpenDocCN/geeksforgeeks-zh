# HTML | DOM Style overflowX 属性

> 原文:[https://www . geesforgeks . org/html-DOM-style-overflow x-property/](https://www.geeksforgeeks.org/html-dom-style-overflowx-property/)

HTML DOM 中的 **Style overflowX** 属性用于指定内容溢出元素左右边缘时的行为。根据该值，内容可以隐藏、显示或显示在滚动条上。

**语法:**

*   它返回 overflowX 属性。

    ```html
    object.style.overflowX
    ```

*   它用于设置 overflowX 属性。

    ```html
    object.style.overflowX = "hidden|visible|scroll|auto|initial|
    inherit"
    ```

**返回值:**返回一个字符串值，代表元素的 overflow-x 属性

**属性值:**

*   **hidden:** The content is clipped and hidden to fit the element. No scrollbars are provided when using this value.
    **Example:**

    ```html
    <!DOCTYPE html>
    <html>

    <head>
        <title>
            DOM Style overflowX Property
        </title>

        <style>
            .content {
                background-color: lightgreen;
                height: 150px;
                width: 200px;
                white-space: nowrap;
            }
        </style>
    </head>

    <body>
        <h1 style="color: green">
            GeeksforGeeks
        </h1>

        <b>DOM Style overflowX Property</b>

        <p>
            The overflowX property specifies the behavior of
            content when it overflows a block-level element’s
            left and right edges.
        </p>

        <div class="content">
            GeeksforGeeks is a computer science portal with a
            huge variety of well written and<br> explained
            computer science and programming articles, quizzes
            and interview questions. <br>The portal also has
            dedicated GATE preparation and competitive
            programming sections.
        </div>

        <button onclick="setOverflow()">
            Change overflowX
        </button>

        <!-- Script to set overflowX to hidden -->
        <script>
            function setOverflow() {
                elem = document.querySelector('.content');
                elem.style.overflowX = 'hidden';
            }
        </script>
    </body>

    </html>                    
    ```

    **输出:**

    *   点击按钮前:
        ![hidden-before](img/225a0f3b3a4a7b2046f74c924920902d.png)
    *   点击按钮后:
        ![hidden-after](img/4b2df3e056810771d61703363b62ab2a.png)
*   **visible:** The content is not clipped and may overflow out to the left or right of the containing element.
    **Example:**

    ```html
    <!DOCTYPE html>
    <html>

    <head>
        <title>
            DOM Style overflowX Property
        </title>

        <style>
            .content {
                background-color: lightgreen;
                height: 150px;
                width: 200px;
                white-space: nowrap;
                overflow-x: hidden;
            }
        </style>
    </head>

    <body>
        <h1 style="color: green">
            GeeksforGeeks
        </h1>

        <b>DOM Style overflowX Property</b>

        <p>
            The overflowX property specifies the behavior of
            content when it overflows a block-level element’s
            left and right edges.
        </p>

        <div class="content">
            GeeksforGeeks is a computer science portal with a
            huge variety of well written and<br> explained
            computer science and programming articles, quizzes
            and interview questions. <br>The portal also has
            dedicated GATE preparation and competitive
            programming sections.
        </div>

        <button onclick="setOverflow()">
            Change overflowX
        </button>

        <!-- Script to set overflowX to visible -->
        <script>
            function setOverflow() {
                elem = document.querySelector('.content');
                elem.style.overflowX = 'visible';
            }
        </script>
    </body>

    </html>                    
    ```

    **输出:**

    *   点击按钮前:
        ![visible-before](img/6940c37a33e1cfdcc8ab5611bd33ad2a.png)
    *   点击按钮后:
        ![visible-after](img/266e9e063b8287e103656914dd3f4c20.png)
*   **scroll:** The content is clipped to fit the element box and a scrollbar is provided help scroll the extra overflowed content. The scrollbar here is added even if the content is not clipped.
    **Example:**

    ```html
    <!DOCTYPE html>
    <html>

    <head>
        <title>
            DOM Style overflowX Property
        </title>

        <style>
            .content {
                background-color: lightgreen;
                height: 150px;
                width: 200px;
                white-space: nowrap;
            }
        </style>
    </head>

    <body>
        <h1 style="color: green">
            GeeksforGeeks
        </h1>

        <b>DOM Style overflowX Property</b>

        <p>
            The overflowX property specifies the behavior of
            content when it overflows a block-level element’s
            left and right edges.
        </p>

        <div class="content">
            GeeksforGeeks is a computer science portal with a
            huge variety of well written and<br> explained
            computer science and programming articles, quizzes
            and interview questions. <br>The portal also has
            dedicated GATE preparation and competitive
            programming sections.
        </div>

        <button onclick="setOverflow()">
            Change overflowX
        </button>

        <!-- Script to set overflowX to scroll -->    
        <script>
            function setOverflow() {
                elem = document.querySelector('.content');
                elem.style.overflowX = 'scroll';
            }
        </script>
    </body>
    </html>                    
    ```

    **输出:**

    *   点击按钮前:
        ![scroll-before](img/df914c50cfb23a1152e119ad2f883502.png)
    *   点击按钮后:
        ![scroll-after](img/1e63dffe853a41204831f73f55fefb20.png)
*   **auto:** The behavior of auto depends on the content and scrollbars are added only when the content overflows.
    **Example:**

    ```html
    <!DOCTYPE html>
    <html>

    <head>
        <title>
            DOM Style overflowX Property
        </title>

        <style>
            .content {
                background-color: lightgreen;
                height: 150px;
                width: 200px;
                white-space: nowrap;
            }
        </style>
    </head>

    <body>
        <h1 style="color: green">
            GeeksforGeeks
        </h1>

        <b>DOM Style overflowX Property</b>

        <p>
            The overflowX property specifies the behavior of
            content when it overflows a block-level element’s
            left and right edges.
        </p>

        <div class="content">
            GeeksforGeeks is a computer science portal with a
            huge variety of well written and<br> explained
            computer science and programming articles, quizzes
            and interview questions. <br>The portal also has
            dedicated GATE preparation and competitive
            programming sections.
        </div>

        <button onclick="setOverflow()">
            Change overflowX
        </button>

        <!-- Script to set overflowX to auto -->
        <script>
            function setOverflow() {
                elem = document.querySelector('.content');
                elem.style.overflowX = 'auto';
            }
        </script>
    </body>

    </html>                    
    ```

    **输出:**

    *   点击按钮前:
        ![auto-before](img/35d4dcb5e5f7e9476928334847e84d31.png)
    *   点击按钮后:
        ![auto-after](img/f0a8ecf7dfc5503212a28e3990047b2d.png)
*   **initial:** This is used to set this property to its default value.
    **Example:**

    ```html
    <!DOCTYPE html>
    <html>

    <head>
        <title>
            DOM Style overflowX Property
        </title>

        <style>
            .content {
                background-color: lightgreen;
                height: 150px;
                width: 200px;
                white-space: nowrap;

                /* Setting the overflow-x property to 'scroll' to
                observe the effect of initial */
                overflow-x: scroll;
            }
        </style>
    </head>

    <body>
        <h1 style="color: green">
            GeeksforGeeks
        </h1>

        <b>DOM Style overflowX Property</b>

        <p>
            The overflowX property specifies the behavior of
            content when it overflows a block-level element’s
            left and right edges.
        </p>

        <div class="content">
            GeeksforGeeks is a computer science portal with a
            huge variety of well written and<br> explained
            computer science and programming articles, quizzes
            and interview questions. <br>The portal also has
            dedicated GATE preparation and competitive
            programming sections.
        </div>

        <button onclick="setOverflow()">
            Change overflowX
        </button>

        <!-- Script to set overflowX to initial -->
        <script>
            function setOverflow() {
                elem = document.querySelector('.content');
                elem.style.overflowX = 'initial';
            }
        </script>
    </body>
    </html>                    
    ```

    **输出:**

    *   点击按钮前:
        ![initial-before](img/9647181e3b2be6afb75d8527475a8f3d.png)
    *   点击按钮后:
        ![initial-after](img/9ce50fa09dfb567783d076a853b8d3a9.png)
*   **inherit:** It inherits the property from its parent element.
    **Example:**

    ```html
    <!DOCTYPE html>
    <html>

    <head>
        <title>
            DOM Style overflowX Property
        </title>

        <style>
            #parent {

                /* Setting the overflow-x property
                of the parent */
                overflow-x: hidden;
            }
            .content {
                background-color: lightgreen;
                height: 150px;
                width: 200px;
                white-space: nowrap;
            }
        </style>
    </head>

    <body>
        <h1 style="color: green">
            GeeksforGeeks
        </h1>

        <b>DOM Style overflowX Property</b>

        <p>
            The overflowX property specifies the behavior of
            content when it overflows a block-level element’s
            left and right edges.
        </p>

        <div id="parent">
            <div class="content">
                GeeksforGeeks is a computer science portal
                with a huge variety of well written and <br>
                explained computer science and programming 
                articles, quizzes and interview questions.
                <br>The portal also has dedicated GATE 
                preparation and competitive programming 
                sections.
            </div>
        </div>

        <button onclick="setOverflow()">
            Change overflowX
        </button>

        <!-- Script to use overflowX to inherit -->
        <script>
            function setOverflow() {
                elem = document.querySelector('.content');
                elem.style.overflowX = 'inherit';
            }
        </script>
    </body>

    </html>                    
    ```

    **输出:**

    *   点击按钮前:
        ![inherit-before](img/baac3be1535cbafcd8250325af3aa136.png)
    *   点击按钮后:
        ![inherit-after](img/0b7d0537abac3aa475fc2c3ffe1a3e60.png)

    **支持的浏览器:**T2 DOM Style overflow x 属性支持的浏览器如下:

    *   谷歌 Chrome
    *   微软公司出品的 web 浏览器
    *   火狐浏览器
    *   歌剧
    *   苹果 Safari