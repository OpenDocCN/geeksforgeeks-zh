# HTML | DOM Style objectFit 属性

> 原文:[https://www . geesforgeks . org/html-DOM-style-object fit-property/](https://www.geeksforgeeks.org/html-dom-style-objectfit-property/)

HTML DOM 中的 **Style objectFit** 属性用于**设置**或**返回**如何调整图像或视频元素的大小以适合其容器。

**语法:**

*   它返回 objectFit 属性。

    ```html
    object.style.objectFit
    ```

*   它用于设置 objectFit 属性。

    ```html
    object.style.objectFit = "contain|cover|scale-down|none|fill|
    initial|inherit"
    ```

**返回值:**它返回一个字符串值，代表元素的对象拟合

**属性值:**

*   **contain:** The replaced content is scaled to maintain its aspect ratio while also fitting the content box.

    **示例-1:**

    ```html
    <!DOCTYPE html>
    <html>

    <head>
        <title>
          DOM Style objectFit Property
        </title>
        <style>
            #content {
                border: solid;
                height: 250px;
                width: 400px;
            }
        </style>
    </head>

    <body>
        <h1 style="color: green">
          GeeksforGeeks
        </h1>
        <b>
          DOM Style objectFit Property
        </b>
        <p>
            <img src=
    "https://media.geeksforgeeks.org/wp-content/uploads/20190314004249/sample-image2.png" 
                 id="content" />
        </p>
        <button onclick="setObjectFit()">
            Change objectFit
        </button>

        <!-- Script to set objectFit to contain -->
        <script>
            function setObjectFit() {
                elem = document.querySelector('#content');
                elem.style.objectFit = 'contain';
            }
        </script>
    </body>

    </html>
    ```

    **输出:**

    *   Before clicking the button:

        ![contain-before](img/8f600e3b5ba1bfb10a487903929d47bb.png)

    *   After clicking the button:

        ![contain-after](img/82de00150cadc0f68e4debabf6abac15.png)

*   **cover:** The replaced content is sized to maintain its aspect ratio while filling the element’s entire content box. The object may be clipped to fit the content box if required.

    **示例-2:**

    ```html
    <!DOCTYPE html>
    <html>

    <head>
        <title>
          DOM Style objectFit Property
        </title>
        <style>
            #content {
                border: solid;
                height: 250px;
                width: 400px;
            }
        </style>
    </head>

    <body>
        <h1 style="color: green">
          GeeksforGeeks
        </h1>
        <b>
          DOM Style objectFit Property
        </b>
        <p>
            <img src=
    "https://media.geeksforgeeks.org/wp-content/uploads/20190314004249/sample-image2.png"
                 id="content" />
        </p>
        <button onclick="setObjectFit()">
            Change objectFit
        </button>

        <!-- Script to set objectFit to cover -->
        <script>
            function setObjectFit() {
                elem = document.querySelector('#content');
                elem.style.objectFit = 'cover';
            }
        </script>
    </body>

    </html>
    ```

    **输出:**

    *   Before clicking the button:

        ![cover-before](img/ae3c7fef786efc6ac610c9ee806df784.png)

    *   After clicking the button:

        ![cover-after](img/8c3ea1a91ec5385373605e236e060ecd.png)

        *   **scale-down:** The replaced image is resized as if none or contain were specified and it results to the smallest object size.

    **示例-3:**

    ```html
    <!DOCTYPE html>
    <html>

    <head>
        <title>
          DOM Style objectFit Property
        </title>
        <style>
            #content {
                border: solid;
                height: 250px;
                width: 400px;
            }
        </style>
    </head>

    <body>
        <h1 style="color: green">
          GeeksforGeeks
        </h1>
        <b>
          DOM Style objectFit Property
        </b>
        <p>
            <img src=
    "https://media.geeksforgeeks.org/wp-content/uploads/20190314004249/sample-image2.png"
                 id="content" />
        </p>
        <button onclick="setObjectFit()">
            Change objectFit
        </button>

        <!-- Script to set objectFit to scale-down -->
        <script>
            function setObjectFit() {
                elem = document.querySelector('#content');
                elem.style.objectFit = 'scale-down';
            }
        </script>
    </body>

    </html>
    ```

    **输出:**

    *   Before clicking the button:

        ![scale-down-before](img/50e461ef3788cf1bed4d23edd13eab6c.png)

    *   After clicking the button:

        ![scale-down-after](img/d54c1a3c0ba190be3f67b1c3e6d77bbf.png)

        *   **none:** The replaced content is not resized.

    **示例-4:**

    ```html
    <!DOCTYPE html>
    <html>

    <head>
        <title>
          DOM Style objectFit Property
        </title>
        <style>
            #content {
                border: solid;
                height: 250px;
                width: 400px;
            }
        </style>
    </head>

    <body>
        <h1 style="color: green">
          GeeksforGeeks
        </h1>
        <b>
          DOM Style objectFit Property
        </b>
        <p>
            <img src=
    "https://media.geeksforgeeks.org/wp-content/uploads/20190314004249/sample-image2.png" 
                 id="content" />
        </p>
        <button onclick="setObjectFit()">
            Change objectFit
        </button>

        <!-- Script to set objectFit to none -->
        <script>
            function setObjectFit() {
                elem = document.querySelector('#content');
                elem.style.objectFit = 'none';
            }
        </script>
    </body>

    </html>
    ```

    **输出:**

    *   Before clicking the button:

        ![none-before](img/c45fcc6a916e347ed096c505372b5883.png)

    *   After clicking the button:

        ![none-after](img/02f77399aa51227b981704b8e481cb54.png)

        *   **fill:** The content is resized to fill the element’s content box. This is the default value.

    **示例-5:**

    ```html
    <!DOCTYPE html>
    <html>

    <head>
        <title>
          DOM Style objectFit Property
        </title>
        <style>
            #content {
                border: solid;
                height: 250px;
                width: 400px;
                object-fit: scale-down;
            }
        </style>
    </head>

    <body>
        <h1 style="color: green">
          GeeksforGeeks
        </h1>
        <b>
          DOM Style objectFit Property
        </b>
        <p>
            <img src=
    "https://media.geeksforgeeks.org/wp-content/uploads/20190314004249/sample-image2.png" 
                 id="content" />
        </p>
        <button onclick="setObjectFit()">
            Change objectFit
        </button>

        <!-- Script to set objectFit to fill -->
        <script>
            function setObjectFit() {
                elem = document.querySelector('#content');
                elem.style.objectFit = 'fill';
            }
        </script>
    </body>

    </html>
    ```

    **输出:**

    *   Before clicking the button:

        ![fill-before](img/b63a59b944f0e33d13d7402db209c057.png)

    *   After clicking the button:

        ![fill-after](img/0b19a8c50e0b46dfd903be3f7339e0d3.png)

        *   **initial:** This is used to set this property to its default value.

    **示例-6:**

    ```html
    <!DOCTYPE html>
    <html>

    <head>
        <title>
          DOM Style objectFit Property
        </title>
        <style>
            #content {
                border: solid;
                height: 250px;
                width: 400px;
                object-fit: scale-down;
            }
        </style>
    </head>

    <body>
        <h1 style="color: green">
          GeeksforGeeks
        </h1>
        <b>
          DOM Style objectFit Property
        </b>
        <p>
            <img src=
    "https://media.geeksforgeeks.org/wp-content/uploads/20190314004249/sample-image2.png" 
                 id="content" />
        </p>
        <button onclick="setObjectFit()">
            Change objectFit
        </button>

        <!-- Script to set objectFit to initial -->
        <script>
            function setObjectFit() {
                elem = document.querySelector('#content');
                elem.style.objectFit = 'initial';
            }
        </script>
    </body>

    </html>
    ```

    **输出:**

    *   Before clicking the button:

        ![initial-before](img/9beecb356c3858d65b13cc787545ae95.png)

    *   After clicking the button:

        ![initial-after](img/2669093e85ee9e3552ae494911da2b9c.png)

        *   **inherit:** This inherits the property from its parent.

    **示例-7:**

    ```html
    <!DOCTYPE html>
    <html>

    <head>
        <title>
          DOM Style objectFit Property
        </title>
        <style>
            #parent {
                object-fit: contain;
            }

            #content {
                border: solid;
                height: 250px;
                width: 400px;
            }
        </style>
    </head>

    <body>
        <h1 style="color: green">
          GeeksforGeeks
        </h1>
        <b>
          DOM Style objectFit Property
        </b>
        <p id="parent">
            <img src=
    "https://media.geeksforgeeks.org/wp-content/uploads/20190314004249/sample-image2.png"
                 id="content" />
        </p>
        <button onclick="setObjectFit()">
            Change objectFit
        </button>

        <!-- Script to set objectFit to inherit -->
        <script>
            function setObjectFit() {
                elem = document.querySelector('#content');
                elem.style.objectFit = 'inherit';
            }
        </script>
    </body>

    </html>
    ```

    **输出:**

    *   Before clicking the button:

        ![inherit-before](img/2a788f4d5e25559113914a9019490980.png)

    *   After clicking the button:

        ![inherit-after](img/0160518c8e346fe11b77eff37bd6c7a8.png)

**支持的浏览器:**以下列出了 *objectFit* 属性支持的浏览器:

*   谷歌 Chrome 31.0
*   Internet Explorer 16.0
*   Firefox 36.0
*   Opera 19.0
*   苹果 Safari 7.1