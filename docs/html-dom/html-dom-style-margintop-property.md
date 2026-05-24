# HTML | DOM 样式边距属性

> 原文:[https://www . geesforgeks . org/html-DOM-style-margin top-property/](https://www.geeksforgeeks.org/html-dom-style-margintop-property/)

HTML DOM 中的**样式边距属性**用于设置或返回元素的上边距。

**语法:**

*   它返回 marginTop 属性。

    ```html
    object.style.marginTop
    ```

*   它用于设置 marginTop 属性。

    ```html
    object.style.marginTop = "length|percentage|auto|initial|
    inherit"
    ```

**返回值:**它返回一个代表元素上边距的字符串值

**属性值:**

*   **length:** It is used to specify the margin in fixed units. Its default value is 0.

    **示例:**

    ```html
    <!DOCTYPE html>
    <html>

    <head>
        <title>
            DOM Style marginTop Property
        </title>
    </head>

    <body>
        <h1 style="color: green">
            GeeksforGeeks
        </h1>

        <b>DOM Style marginTop Property</b>

        <div class="container">
            <div class="div1">Line One</div>
            <div class="div2">Line Two</div>

            <button onclick="setMargin()">
                Change marginTop
            </button>
        </div>

        <!-- Script to set top margin -->
        <script>
            function setMargin() {
                elem = document.querySelector('.div1');
                elem.style.marginTop = '50px';
            }
        </script>
    </body>

    </html>                    
    ```

    **输出:**

    *   Before clicking the button:
        ![length-before](img/cea62d89a3a3262237c9a9938d7cf6a7.png)

        点击按钮后:
        ![length-after](img/19933c9b9258b610dd30752adc45c45e.png)

*   **percentage:** It is used to specify the amount of margin as a percentage relative to the width of the containing element.

    **示例:**

    ```html
    <!DOCTYPE html>
    <html>

    <head>
        <title>
            DOM Style marginTop Property
        </title>
    </head>

    <body>
        <h1 style="color: green">
            GeeksforGeeks
        </h1>

        <b>DOM Style marginTop Property</b>

        <div class="container">
            <div class="div1">Line One</div>
            <div class="div2">Line Two</div>

            <button onclick="setMargin()">
                Change marginTop
            </button>
        </div>

        <!-- Script to set top margin -->
        <script>
            function setMargin() {
                elem = document.querySelector('.div1');
                elem.style.marginTop = '20%';
            }
        </script>
    </body>

    </html>                    
    ```

    **输出:**

    *   点击按钮前:
        ![percentage-before](img/eca729a1dec4747a797b38b9cd55f635.png)
    *   点击按钮后:
        ![percentage-after](img/658d2bc91d3727df7501a05b72859e7a.png)
*   **auto:** If the value is set to ‘auto’, then the browser automatically calculates a suitable value for the margin size.

    **示例:**

    ```html
    <!DOCTYPE html>
    <html>

    <head>
        <title>
            DOM Style marginTop Property
        </title>
    </head>

    <body>
        <h1 style="color: green">
            GeeksforGeeks
        </h1>

        <b>DOM Style marginTop Property</b>

        <div class="container">
            <div class="div1" style="margin-top: 50px;">
                Line One
            </div>

            <div class="div2">
                Line Two
            </div>

            <button onclick="setMargin()">
                Change marginTop
            </button>
        </div>

        <!-- Script to set top margin -->
        <script>
            function setMargin() {
                elem = document.querySelector('.div1');
                elem.style.marginTop = 'auto';
            }
        </script>
    </body>

    </html>                    
    ```

    **输出:**

    *   Before clicking the button:
        ![auto-before](img/6da744b44942d33a71fe8d69a16c77fe.png)

        点击按钮后:
        ![auto-after](img/63ffea32212c3a20220e07f70e01193d.png)

*   **initial:** It is used to set the property to its default value.

    **示例:**

    ```html
    <!DOCTYPE html>
    <html>

    <head>
        <title>
            DOM Style marginTop Property
        </title>
    </head>

    <body>
        <h1 style="color: green">
            GeeksforGeeks
        </h1>

        <b>DOM Style marginTop Property</b>

        <div class="container">

            <div class="div1" style="margin-top: 50px;">
                Line One
            </div>

            <div class="div2">
                Line Two
            </div>

            <button onclick="setMargin()">
                Change marginTop
            </button>
        </div>

        <!-- Script to set top margin -->
        <script>
            function setMargin() {
                elem = document.querySelector('.div1');
                elem.style.marginTop = 'initial';
            }
        </script>
    </body>

    </html>                    
    ```

    **输出:**

    *   点击按钮前:
        ![initial-before](img/0a4bc304c2cba1786c92a53bb2638c8e.png)
    *   点击按钮后:
        ![initial-after](img/1c072a6fc3b15c83b114110b16df802f.png)
*   **inherit:** It is used to inherit the value from its parent element.

    **示例:**

    ```html
    <!DOCTYPE html>
    <html>

    <head>
        <title>
            DOM Style marginTop Property
        </title>
    </head>

    <body>
        <h1 style="color: green">
            GeeksforGeeks
        </h1>

        <b>DOM Style marginTop Property</b>

        <div class="container">
            <div class="div1" style="margin-top: 50px;">
                Line One
            </div>

            <div class="div2">
                Line Two
            </div>

            <button onclick="setMargin()">
                Change marginTop
            </button>
        </div>

        <!-- Script to set top margin -->
        <script>
            function setMargin() {
                elem = document.querySelector('.div1');
                elem.style.marginTop = 'inherit';
            }
        </script>
    </body>

    </html>                    
    ```

    **输出:**

*   点击按钮前:
    ![inherit-before](img/1217db223fccb880892d3ecd299e4f3a.png)
*   点击按钮后:
    ![inherit-after](img/51bee90bf8c19ea399f2af63653979a3.png)

**支持的浏览器:**由 *DOM Style marginTop 属性*支持的浏览器如下:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   歌剧
*   旅行队