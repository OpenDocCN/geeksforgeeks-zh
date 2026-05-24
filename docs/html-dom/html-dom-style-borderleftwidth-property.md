# HTML | DOM 样式边框扭曲属性

> 原文:[https://www . geesforgeks . org/html-DOM-style-bordereftwidth-property/](https://www.geeksforgeeks.org/html-dom-style-borderleftwidth-property/)

DOM Style **边框扭曲**属性用于**设置**或**返回** *元素左边框的宽度*。

**语法:**

*   获取边界扭曲属性

    ```html
    object.style.borderLeftWidth
    ```

*   设置边框扭曲属性

    ```html
    object.style.borderLeftWidth = "thin | medium | thick | length |
    initial | inherit"
    ```

**返回值:**返回一个字符串值，代表元素左边框的宽度。

**属性值:**

1.  **thin:** This is used to define a thin left border.

    **示例-1:**

    ```html
    <!DOCTYPE html>
    <html lang="en">

    <head>
        <title>
          DOM Style BorderLeftWidth
        </title>

        <style>
            .elem {
                padding: 10px;
                border-style: solid;
            }
        </style>
    </head>

    <body>
        <h1 style="color: green">
          GeeksforGeeks
        </h1>
        <b>
          DOM Style BorderLeftWidth
        </b>
        <p class="elem">
            GeeksforGeeks is a computer science
          portal with a huge variety of well written and
          explained computer science and programming
          articles, quizzes and interview questions.
        </p>
        <button onclick="changeWidth()">
          Change BorderLeftWidth
        </button>

        <!-- Script to change BorderLeftWidth -->
        <script>
            function changeWidth() {
                elem = document.querySelector('.elem');
                elem.style.borderLeftWidth = 'thin';
            }
        </script>
    </body>

    </html>
    ```

    **输出:**

    **点击按钮前:**

    ![thin-before](img/9d8b83d3a6baa1faba3a4b627e8bed21.png)

    **点击按钮后:**

    ![thin-after](img/93d4a80a11f7368d7bb12d238ab83230.png)

2.  **medium:** This is used to define a medium left border. This is the default value.

    **示例-2:**

    ```html
    <!DOCTYPE html>
    <html lang="en">

    <head>
        <title>
          DOM Style BorderLeftWidth
        </title>
        <style>
            .elem {
                padding: 10px;
                border-style: solid;
                border-left-width: thin;
            }
        </style>
    </head>

    <body>
        <h1 style="color: green">
          GeeksforGeeks
        </h1>
        <b>
          DOM Style BorderLeftWidth
        </b>
        <p class="elem">
            GeeksforGeeks is a computer science
          portal with a huge variety of well
          written and explained computer 
          science and programming articles, 
          quizzes and interview questions.
        </p>
        <button onclick="changeWidth()">
          Change BorderLeftWidth
        </button>

        <!-- Script to change BorderLeftWidth -->
        <script>
            function changeWidth() {
                elem = document.querySelector('.elem');
                elem.style.borderLeftWidth = 'medium';
            }
        </script>
    </body>

    </html>
    ```

    **输出:**

    **点击按钮前:**

    ![medium-before](img/2131dfc14cf376c9cfda6bc277f916b8.png)

    **点击按钮后:**

    ![medium-after](img/9d82c6c27f9abeac2a95753330c0dfd9.png)

3.  **thick:** This is used to define a thick left border.

    **示例-3:**

    ```html
    <!DOCTYPE html>
    <html lang="en">

    <head>
        <title>
          DOM Style BorderLeftWidth
        </title>

        <style>
            .elem {
                padding: 10px;
                border-style: solid;
            }
        </style>
    </head>

    <body>
        <h1 style="color: green">
          GeeksforGeeks
        </h1>
        <b>
          DOM Style BorderLeftWidth
        </b>
        <p class="elem">
          GeeksforGeeks is a computer science
          portal with a huge variety of well
          written and explained computer science
          and programming articles, quizzes 
          and interview questions.
        </p>
        <button onclick="changeWidth()">
          Change BorderLeftWidth
        </button>

        <!-- Script to change BorderLeftWidth -->
        <script>
            function changeWidth() {
                elem = document.querySelector('.elem');
                elem.style.borderLeftWidth = 'thick';
            }
        </script>
    </body>

    </html>
    ```

    **输出:**

    **点击按钮前:**

    ![thick-before](img/e61072fbb971f51363aac7c404f11382.png)

    **点击按钮后:**

    ![thick-after](img/43382fef00dfac14d88fa9d67533e450.png)

4.  **length:** This is used to define the left border width in terms of length units.

    **示例-4:**

    ```html
    <!DOCTYPE html>
    <html lang="en">

    <head>
        <title>
          DOM Style BorderLeftWidth
        </title>

        <style>
            .elem {
                padding: 10px;
                border-style: solid;
            }
        </style>
    </head>

    <body>
        <h1 style="color: green">
          GeeksforGeeks
        </h1>
        <b>
          DOM Style BorderLeftWidth
        </b>
        <p class="elem">
          GeeksforGeeks is a computer science portal
          with a huge variety of well written and 
          explained computer science and programming
          articles, quizzes and interview questions.
        </p>
        <button onclick="changeWidth()">
          Change BorderLeftWidth
        </button>

        <!-- Script to change BorderLeftWidth -->
        <script>
            function changeWidth() {
                elem = document.querySelector('.elem');
                elem.style.borderLeftWidth = '10px';
            }
        </script>
    </body>

    </html>
    ```

    **输出:**

    **点击按钮前:**

    ![length-before](img/ffff0b50c07fe8b0d7fdbc0654bd6569.png)

    **点击按钮后:**

    ![length-after](img/f795302ef255f5f3616ce56fb6f5149c.png)

5.  **initial:** This is used to set this property to its default value.

    **示例-5:**

    ```html
    <!DOCTYPE html>
    <html lang="en">

    <head>
        <title>
          DOM Style BorderLeftWidth
        </title>

        <style>
            .elem {
                padding: 10px;
                border-style: solid;
                border-left-width: 15px;
            }
        </style>
    </head>

    <body>
        <h1 style="color: green">
          GeeksforGeeks
        </h1>
        <b>
          DOM Style BorderLeftWidth
        </b>
        <p class="elem">
            GeeksforGeeks is a computer science portal
          with a huge variety of well written and explained
          computer science and programming articles, quizzes
          and interview questions.
        </p>
        <button onclick="changeWidth()">
          Change BorderLeftWidth
        </button>

        <!-- Script to change BorderLeftWidth -->
        <script>
            function changeWidth() {
                elem = document.querySelector('.elem');
                elem.style.borderLeftWidth = 'initial';
            }
        </script>
    </body>

    </html>
    ```

    **输出:**

    **点击按钮前:**

    ![initial-before](img/a29265eccd6aa5868829c0d9f01b2e09.png)

    **点击按钮后:**

    ![initial-after](img/c31bf1fcf6491762d5e2c77047891e94.png)

6.  **inherit:** This inherits the property from its parent.

    **示例-6:**

    ```html
    <!DOCTYPE html>
    <html lang="en">

    <head>
        <title>
          DOM Style BorderLeftWidth
        </title>

        <style>
            #parent {
                padding: 10px;
                border-style: solid;
                border-left-width: 15px;
            }

            .elem {
                padding: 10px;
                border-style: solid;
            }
        </style>
    </head>

    <body>
        <h1 style="color: green">
          GeeksforGeeks
        </h1>
        <b>
          DOM Style BorderLeftWidth
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
        <button onclick="changeWidth()">
          Change BorderLeftWidth
        </button>

        <!-- Script to change BorderLeftWidth -->
        <script>
            function changeWidth() {
                elem = document.querySelector('.elem');
                elem.style.borderLeftWidth = 'inherit';
            }
        </script>
    </body>

    </html>
    ```

    **输出:**

    **点击按钮前:**

    ![inherit-before](img/d6d920d05935f3c4ad5d88a8dfdb398f.png)

    **点击按钮后:**

    ![inherit-after](img/cfa0c2070f844394df832da51bead21a.png)

    **支持的浏览器:**T2【边界扭曲】属性支持的浏览器如下:

    *   谷歌 Chrome
    *   微软公司出品的 web 浏览器
    *   火狐浏览器
    *   歌剧
    *   苹果 Safari