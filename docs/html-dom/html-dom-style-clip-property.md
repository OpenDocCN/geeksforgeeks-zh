# HTML | DOM 样式剪辑属性

> 原文:[https://www.geeksforgeeks.org/html-dom-style-clip-property/](https://www.geeksforgeeks.org/html-dom-style-clip-property/)

HTML DOM 中的**样式剪辑**属性用于**设置**或**返回** *定位元素的可见部分。*

**语法:**

*   它返回剪辑属性。

    ```html
    object.style.clip
    ```

*   它用于设置剪辑属性。

    ```html
    object.style.clip = "rect(top right bottom left)|normal|initial|
    inherit"
    ```

**返回值:**返回一个字符串值，代表定位元素可见的部分。

**属性值:**

*   **rect(top right bottom left):** This value is used to clip the element in a rectangular shape. The top, right, bottom and left values are used to define the points of the rectangle.

    **示例-1:**

    ```html
    <!DOCTYPE html>
    <html>

    <head>
        <title>
          DOM Style clip Property
        </title>
        <style>
            #myImage {
                position: absolute;
            }

            button {
                margin-top: 400px;
            }
        </style>
    </head>

    <body>
        <h1 style="color: green">
          GeeksforGeeks
        </h1>
        <b>DOM Style clip Property</b>
        <p>
            The clip property is used to specify 
          the part of a positioned element that is visible.
        </p>

        <img src=
    "https://media.geeksforgeeks.org/wp-content/uploads/20190311222622/sample-image.png" 
             id="myImage">

        <button onclick="setClip()">
          Set Clip Property
        </button>

        <!-- Script to set clip to rect() -->
        <script>
            function setClip() {
              elem = 
                document.querySelector('#myImage');

              elem.style.clip = 
                'rect(75px 250px 250px 75px)';
            }
        </script>
    </body>

    </html>
    ```

    **输出:**

    **点击按钮前:**
    ![clip-before](img/2074c75e6b53abd4de333a267ae2b127.png)

    **点击按钮后:**
    ![clip-after](img/9fba543837121ae76cbadc03d1594678.png)

*   **normal:** This value does not clip the element. This is the default value.

    **示例-2:**

    ```html
    <!DOCTYPE html>
    <html>

    <head>
        <title>
          DOM Style clip Property
        </title>
        <style>
            #myImage {
              position: absolute;
              clip: rect(50px 200px 200px 50px);
            }

            button {
                margin-top: 400px;
            }
        </style>
    </head>

    <body>
        <h1 style="color: green">
          GeeksforGeeks
        </h1>
        <b>DOM Style clip Property</b>
        <p>
            The clip property is used to specify
            the part of a positioned element
            that is visible.
        </p>

        <img src=
    "https://media.geeksforgeeks.org/wp-content/uploads/20190311222622/sample-image.png"
             id="myImage">

        <button onclick="setClip()">
          Set Clip Property
        </button>

        <!-- Script to set clip to auto -->
        <script>
            function setClip() {
                elem = 
                  document.querySelector('#myImage');

                elem.style.clip = 'auto';
            }
        </script>
    </body>

    </html>
    ```

    **输出:**

    **点击按钮前:**
    ![normal-before](img/423dfba5cb7355d29e677c6959fcbfd5.png)

    **点击按钮后:**
    ![normal-after](img/fb161ba7e93f45e48c7b59ac6b114928.png)

*   **initial:** This is used to set this property to its default value.

    **示例-3:**

    ```html
    <!DOCTYPE html>
    <html>

    <head>
        <title>
          DOM Style clip Property
        </title>

        <style>
            #myImage {
              position: absolute;
              clip: rect(75px 300px 300px 75px);
            }

            button {
                margin-top: 400px;
            }
        </style>
    </head>

    <body>
        <h1 style="color: green">
          GeeksforGeeks
        </h1>
        <b>
          DOM Style clip Property
        </b>
        <p>
            The clip property is used to specify
            the part of a positioned element 
            that is visible.
        </p>

        <img src=
    "https://media.geeksforgeeks.org/wp-content/uploads/20190311222622/sample-image.png"
             id="myImage">

        <button onclick="setClip()">
          Set Clip Property
        </button>

        <!-- Script to set clip to initial -->
        <script>
            function setClip() {
                elem = 
                  document.querySelector(
                  '#myImage');

                elem.style.clip = 'initial';
            }
        </script>
    </body>

    </html>
    ```

    **输出:**

    **点击按钮前:**
    ![initial-before](img/9a95f17d7373a157a805745f36b220e8.png)

    **点击按钮后:**
    ![initial-after](img/c86083f4c58e8d7af9d4ca2a3d0eed8d.png)

*   **inherit:** This inherits the property from its parent.
    **Example-4:**

    ```html
    <!DOCTYPE html>
    <html>

    <head>
        <title>
          DOM Style clip Property
        </title>

        <style>
         #parent {
            clip: rect(75px 300px 300px 75px);
          }

            #myImage {
                position: absolute;
            }

            button {
                margin-top: 400px;
            }
        </style>
    </head>

    <body>
        <h1 style="color: green">
          GeeksforGeeks
        </h1>

        <b>DOM Style clip Property</b>
        <p>
            The clip property is used to specify
          the part of a positioned element that 
          is visible.
        </p>

        <div id="parent">
            <img src=
    "https://media.geeksforgeeks.org/wp-content/uploads/20190311222622/sample-image.png" 
                 id="myImage">
        </div>
        <button onclick="setClip()">
          Set Clip Property
        </button>

        <!-- Script to set clip to inherit -->
        <script> 
          function setClip() {
            elem = 
              document.querySelector(
              '#myImage');

            elem.style.clip = 'inherit';
            }
        </script>
    </body>

    </html>
    ```

    **输出:**

    **点击按钮前:**
    ![inherit-before](img/5a13b1ef183bdcfe7f1c471b8f237c48.png)

    **点击按钮后:**
    ![inherit-after](img/416032aabbd5c835a0176522b3e1e99b.png)

**支持的浏览器:***DOM Style 剪辑*属性支持的浏览器如下:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   歌剧
*   苹果 Safari