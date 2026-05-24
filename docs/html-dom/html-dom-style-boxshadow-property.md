# HTML | DOM 样式框阴影属性

> 原文:[https://www . geesforgeks . org/html-DOM-style-box shadow-property/](https://www.geeksforgeeks.org/html-dom-style-boxshadow-property/)

DOM Style **boxShadow** 属性用于**设置**或**返回** *元素的投影。*

**语法:**

*   获取盒子阴影属性

    ```html
    object.style.boxShadow
    ```

*   设置框阴影属性

    ```html
    object.style.boxShadow = "horizontal-offset vertical-offset blur
    spread color inset | none | initial | inherit"
    ```

**返回值:**返回一个字符串值，代表元素的盒影属性。

**属性值:**

1.  **horizontal-offset vertical-offset:** This is used to specify the position of the shadow in length units. Negative values are allowed.

    **示例-1:**

    ```html
    <!DOCTYPE html>
    <html lang="en">

    <head>
        <title>
            DOM Style boxShadow
        </title>

        <style>
            .elem {
                border-style: solid;
                margin: 10px;
                padding: 10px;
            }
        </style>
    </head>

    <body>
        <h1 style="color: green">
          GeeksforGeeks
        </h1>
        <b>
          DOM Style boxShadow
        </b>
        <p class="elem">
          GeeksforGeeks is a computer science portal
          with a huge variety of well written and 
          explained computer science and programming
          articles, quizzes and interview questions.
        </p>
        <button onclick="setShadow()" 
                style="margin-top: 20px;">
            Change boxShadow
        </button>

        <!-- Script to change boxShadow -->
        <script>
            function setShadow() {
                elem = document.querySelector('.elem');
                elem.style.boxShadow = '10px 20px';
            }
        </script>
    </body>

    </html>
    ```

    **输出:**

    **点击按钮前:**

    ![offsets-before](img/2c22061161a0ca8fc422b83a8302aad6.png)

    **点击按钮后:**

    ![offsets-after](img/4297d4809b49941fc5898785d6755906.png)

2.  **blur:** This is used to define the amount of blur to be used in the shadow.

    **示例-2:**

    ```html
    <!DOCTYPE html>
    <html lang="en">

    <head>
        <title>
            DOM Style boxShadow
        </title>

        <style>
            .elem {
                border-style: solid;
                margin: 10px;
                padding: 10px;
            }
        </style>
    </head>

    <body>
        <h1 style="color: green">
          GeeksforGeeks
        </h1>
        <b>
          DOM Style boxShadow
        </b>
        <p class="elem">
          GeeksforGeeks is a computer science
          portal with a huge variety of well 
          written and explained computer science
          and programming articles, quizzes and
          interview questions.
        </p>
        <button onclick="setShadow()" 
                style="margin-top: 20px;">
            Change boxShadow
        </button>

        <!-- Script to change boxShadow -->
        <script>
            function setShadow() {
                elem = document.querySelector('.elem');
                elem.style.boxShadow = '10px 20px 5px';
            }
        </script>
    </body>

    </html>
    ```

    **输出:**

    **点击按钮前:**

    ![blur-before](img/caded029edeb30d3c6d934550d757562.png)

    **点击按钮后:**

    ![blur-after](img/4743528bb499d5770740e437533bcd56.png)

3.  **spread:** This is used to define the amount of spread of the shadow.

    **示例-3:**

    ```html
    <!DOCTYPE html>
    <html lang="en">

    <head>
        <title>
            DOM Style boxShadow
        </title>

        <style>
            .elem {
                border-style: solid;
                margin: 30px;
                padding: 10px;
            }
        </style>
    </head>

    <body>
        <h1 style="color: green">
          GeeksforGeeks
        </h1>
        <b>
          DOM Style boxShadow
        </b>
        <p class="elem">
          GeeksforGeeks is a computer science 
          portal with a huge variety of well 
          written and explained computer science 
          and programming articles, quizzes and
          interview questions.
        </p>
        <button onclick="setShadow()" 
                style="margin-top: 20px;">
            Change boxShadow
        </button>

        <!-- Script to change boxShadow -->
        <script>
            function setShadow() {
                elem = document.querySelector('.elem');
                elem.style.boxShadow = '10px 20px 0px 20px';
            }
        </script>
    </body>

    </html>
    ```

    **输出:**

    **点击按钮前:**

    ![spread-before](img/b80d65c465134f1c6aae91a1b141fe48.png)

    **点击按钮后:**

    ![spread-after](img/171c56df494486964bc4d1389985dda0.png)

4.  **color:** This is used to define the color of the shadow to be used.

    **示例-4:**

    ```html
    <!DOCTYPE html>
    <html lang="en">

    <head>
        <title>
            DOM Style boxShadow
        </title>

        <style>
            .elem {
                border-style: solid;
                margin: 25px;
                padding: 10px;
            }
        </style>
    </head>

    <body>
        <h1 style="color: green">
          GeeksforGeeks
        </h1>
        <b>
          DOM Style boxShadow
        </b>
        <p class="elem">
          GeeksforGeeks is a computer science 
          portal with a huge variety of well 
          written and explained computer science 
          and programming articles, quizzes and 
          interview questions.
        </p>
        <button onclick="setShadow()" 
                style="margin-top: 20px;">
            Change boxShadow
        </button>

        <!-- Script to change boxShadow -->
        <script>
            function setShadow() {
                elem = document.querySelector('.elem');
                elem.style.boxShadow = '10px 20px green';
            }
        </script>
    </body>

    </html>
    ```

    **输出:**

    **点击按钮前:**

    ![color-before](img/538cffdaf9abd3ffa283dbca90470788.png)

    **点击按钮后:**

    ![color-after](img/0c59d1ca977a4bf7616cd36718455706.png)

5.  **inset:** This is used to set the shadow to an inner one. Normally a shadow is an outset, that is outside.

    **示例-5:**

    ```html
    <!DOCTYPE html>
    <html lang="en">

    <head>
        <title>
            DOM Style boxShadow
        </title>

        <style>
            .elem {
                border-style: solid;
                margin: 25px;
                padding: 10px;
                box-shadow: 10px 20px;
            }
        </style>
    </head>

    <body>
        <h1 style="color: green">
          GeeksforGeeks
        </h1>
        <b>
          DOM Style boxShadow
        </b>
        <p class="elem">
          GeeksforGeeks is a computer science 
          portal with a huge variety of well 
          written and explained computer science 
          and programming articles, quizzes and 
          interview questions.
        </p>
        <button onclick="setShadow()" 
                style="margin-top: 20px;">
            Change boxShadow
        </button>

        <!-- Script to change boxShadow -->
        <script>
            function setShadow() {
                elem = document.querySelector('.elem');
                elem.style.boxShadow = '10px 20px inset';
            }
        </script>
    </body>

    </html>
    ```

    **输出:**

    **点击按钮前:**

    ![inset-before](img/91ef85b640f861ffb31e5281a8f1d579.png)

    **点击按钮后:**

    ![inset-after](img/59af8019d36f00eece865c25e58283f1.png)

6.  **none:** This is used to remove any shadow present. This is the default value.

    **示例-6:**

    ```html
    <!DOCTYPE html>
    <html lang="en">

    <head>
        <title>
            DOM Style boxShadow
        </title>

        <style>
            .elem {
                border-style: solid;
                margin: 10px;
                padding: 10px;
                box-shadow: 10px 20px;
            }
        </style>
    </head>

    <body>
        <h1 style="color: green">
          GeeksforGeeks
        </h1>
        <b>
          DOM Style boxShadow
        </b>
        <p class="elem">
          GeeksforGeeks is a computer science
          portal with a huge variety of well 
          written and explained computer science 
          and programming articles, quizzes and 
          interview questions.
        </p>
        <button onclick="setShadow()" 
                style="margin-top: 20px;">
            Change boxShadow
        </button>

        <!-- Script to change boxShadow -->
        <script>
            function setShadow() {
                elem = document.querySelector('.elem');
                elem.style.boxShadow = 'none';
            }
        </script>
    </body>

    </html>
    ```

    **输出:**

    **点击按钮前:**

    ![none-before](img/88216b29f9778d3dbbf9dd796bc53303.png)

    **点击按钮后:**

    ![none-after](img/d454ee87a61a960f4f603052701249b4.png)

7.  **initial:** This is used to set this property to its default value.

    **示例-7:**

    ```html
    <!DOCTYPE html>
    <html lang="en">

    <head>
        <title>
            DOM Style boxShadow
        </title>

        <style>
            .elem {
                border-style: solid;
                padding: 10px;
                margin: 25px;
                box-shadow: 10px 20px green;
            }
        </style>
    </head>

    <body>
        <h1 style="color: green">
          GeeksforGeeks
        </h1>
        <b>
          DOM Style boxShadow
        </b>
        <p class="elem">
          GeeksforGeeks is a computer science 
          portal with a huge variety of well
          written and explained computer science
          and programming articles, quizzes and
          interview questions.
        </p>
        <button onclick="setShadow()"
                style="margin-top: 20px;">
            Change boxShadow
        </button>

        <!-- Script to change boxShadow -->
        <script>
            function setShadow() {
                elem = document.querySelector('.elem');
                elem.style.boxShadow = 'initial';
            }
        </script>
    </body>

    </html>
    ```

    **输出:**

    **点击按钮前:**

    ![initial-before](img/cf03a81433ea415265c7bb20fae1c507.png)

    **点击按钮后:**

    ![initial-after](img/582ec025f04721d6073b995cf61205c7.png)

8.  **inherit:** This inherits the property from its parent.

    **示例-8:**

    ```html
    <!DOCTYPE html>
    <html lang="en">

    <head>
        <title>
            DOM Style boxShadow
        </title>

        <style>
            #parent {
                border-style: solid;
                padding: 10px;
                margin: 25px;
                box-shadow: 5px 10px green;
            }

            .elem {
                border-style: solid;
                padding: 10px;
            }
        </style>
    </head>

    <body>
        <h1 style="color: green">
          GeeksforGeeks
        </h1>
        <b>
          DOM Style boxShadow
        </b>
        <br>
        <br>
        <div id="parent">
            <p class="elem">
              GeeksforGeeks is a computer science
              portal with a huge variety of well 
              written and explained computer science
              and programming articles, quizzes and
              interview questions.
            </p>
        </div>
        <br>
        <button onclick="setShadow()" style="margin-top: 20px;">
            Change boxShadow
        </button>

        <!-- Script to change boxShadow -->
        <script>
            function setShadow() {
                elem = document.querySelector('.elem');
                elem.style.boxShadow = 'inherit';
            }
        </script>
    </body>

    </html>
    ```

    **输出:**

    **点击按钮前:**

    ![inherit-before](img/50f04c9f4714cbe3f135cc6c2519f13d.png)

    **点击按钮后:**

    ![inherit-after](img/39fd972810411332d4a0c9b4cd4f4712.png)

    **支持的浏览器:***box shadow*属性支持的浏览器如下:

    *   谷歌 Chrome
    *   Internet Explorer 9.0
    *   火狐浏览器
    *   歌剧
    *   Apple Safari 5.1.1