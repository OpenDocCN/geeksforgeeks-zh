# HTML | DOM 样式 outlineWidth 属性

> 原文:[https://www . geeksforgeeks . org/html-DOM-style-outlinewidth-property/](https://www.geeksforgeeks.org/html-dom-style-outlinewidth-property/)

DOM Style **outlineWidth** 属性用于设置或返回元素周围轮廓的宽度。轮廓是在元素边框之外的指定元素周围创建的线条，以使特定的元素更加独特和易于区分。

**语法:**

*   它返回 outlineWidth 属性。

    ```html
    object.style.outlineWidth
    ```

*   它用于设置 outlineWidth 属性。

    ```html
    object.style.outlineWidth = "thin|medium|thick|length|initial|
    inherit"
    ```

**返回值:**返回一个字符串值，代表元素轮廓的宽度。

**属性值:**

*   **thin:** It sets the outline width to thin, the outline achieved is thinner than outline specified with width as medium and thick.
    **Example:**

    ```html
    <!DOCTYPE html>
    <html>

    <head>
        <title>
            DOM Style outlineWidth Property
        </title>

        <style>
            .elem {
                outline-style: dashed;
            }
        </style>
    </head>

    <body>
        <h1 style="color: green">
            GeeksforGeeks
        </h1>

        <b>DOM Style OutlineWidth</b>

        <p class="elem">
            GeeksforGeeks is a computer science portal
            with a huge variety of well written and 
            explained computer science and programming
            articles, quizzes and interview questions.
            The portal also has dedicated GATE preparation
            and competitive programming sections.
        </p>

        <button onclick="changeWidth()">
            Change outlineWidth
        </button>

        <!--Script to change the outline width -->
        <script>
            function changeWidth() {
                elem = document.querySelector('.elem');
                elem.style.outlineWidth = 'thin';
            }
        </script>
    </body>

    </html>                    
    ```

    **输出:**

    *   点击按钮前:
        ![thin_before](img/3da50ce1b1b66a44148b56a7276a6e0a.png)
    *   点击按钮后:
        ![thin_after](img/2ec3dc2acf3f69af3a1c1d488945015c.png)
*   **medium:** It sets the outline width to default. The width of the outline is thinner than the outline sets thick and thicker than the outline set as thin.
    **Example:**

    ```html
    <!DOCTYPE html>
    <html>

    <head>
        <title>
            DOM Style outlineWidth Property
        </title>

        <style>
            .elem {
                outline-style: dashed;
                outline-width: thin;
            }
        </style>
    </head>

    <body>
        <h1 style="color: green">
            GeeksforGeeks
        </h1>

        <b>DOM Style OutlineWidth</b>

        <p class="elem">
            GeeksforGeeks is a computer science portal
            with a huge variety of well written and 
            explained computer science and programming
            articles, quizzes and interview questions.
            The portal also has dedicated GATE preparation
            and competitive programming sections.
        </p>

        <button onclick="changeWidth()">
            Change outlineWidth
        </button>

        <!--Script to change the outline width -->
        <script>
            function changeWidth() {
                elem = document.querySelector('.elem');
                elem.style.outlineWidth = 'medium';
            }
        </script>
    </body>

    </html>                    
    ```

    **输出:**

    *   点击按钮前:
        ![medium-before](img/d0f1490b7dcf06965321254b974c518a.png)
    *   点击按钮后:
        ![medium-after](img/b790c9e0a90502179a8fa14ee9f92218.png)
*   **thick:** It sets the outline width to thick, the outline achieved is thicker than outline specified with width as medium and think.
    **Example:**

    ```html
    <!DOCTYPE html>
    <html>

    <head>
        <title>
            DOM Style outlineWidth Property
        </title>

        <style>
            .elem {
                outline-style: dashed;
            }
        </style>
    </head>

    <body>
        <h1 style="color: green">
            GeeksforGeeks
        </h1>

        <b>DOM Style OutlineWidth</b>

        <p class="elem">
            GeeksforGeeks is a computer science portal
            with a huge variety of well written and 
            explained computer science and programming
            articles, quizzes and interview questions.
            The portal also has dedicated GATE preparation
            and competitive programming sections.
        </p>

        <button onclick="changeWidth()">
            Change outlineWidth
        </button>

        <!--Script to change the outline width -->
        <script>
            function changeWidth() {
                elem = document.querySelector('.elem');
                elem.style.outlineWidth = 'thick';
            }
        </script>
    </body>

    </html>                    
    ```

    **输出:**

    *   点击按钮前:
        ![thick-before](img/1ed680be8974b4abea4c4297e874fa46.png)
    *   点击按钮后:
        ![thick-after](img/93eca801f7d1cbdfc011738aab0092fa.png)
*   **length:** It is used to define the outline width in terms of length units.
    **Example:**

    ```html
    <!DOCTYPE html>
    <html>

    <head>
        <title>
            DOM Style outlineWidth Property
        </title>

        <style>
            .elem {
                outline-style: dashed;
            }
        </style>
    </head>

    <body>
        <h1 style="color: green">
            GeeksforGeeks
        </h1>

        <b>DOM Style OutlineWidth</b>

        <p class="elem">
            GeeksforGeeks is a computer science portal
            with a huge variety of well written and 
            explained computer science and programming
            articles, quizzes and interview questions.
            The portal also has dedicated GATE preparation
            and competitive programming sections.
        </p>

        <button onclick="changeWidth()">
            Change outlineWidth
        </button>

        <!--Script to change the outline width -->
        <script>
            function changeWidth() {
                elem = document.querySelector('.elem');
                elem.style.outlineWidth = '10px';
            }
        </script>
    </body>

    </html>                    
    ```

    **输出:**

    *   点击按钮前:
        ![length-before](img/ad1b4c76c857d6ff43b8fc91a059f91d.png)
    *   点击按钮后:
        ![length-after](img/0087d6a489557aa3b6b71b03ac4c61cc.png)
*   **initial:** It is used to set this property to its default value.
    **Example:**

    ```html
    <!DOCTYPE html>
    <html>

    <head>
        <title>
            DOM Style outlineWidth Property
        </title>

        <style>
            .elem {
                outline-style: dashed;
                outline-width: 4px;
            }
        </style>
    </head>

    <body>
        <h1 style="color: green">
            GeeksforGeeks
        </h1>

        <b>DOM Style OutlineWidth</b>

        <p class="elem">
            GeeksforGeeks is a computer science portal
            with a huge variety of well written and 
            explained computer science and programming
            articles, quizzes and interview questions.
            The portal also has dedicated GATE preparation
            and competitive programming sections.
        </p>

        <button onclick="changeWidth()">
            Change outlineWidth
        </button>

        <!--Script to change the outline width -->
        <script>
            function changeWidth() {
                elem = document.querySelector('.elem');
                elem.style.outlineWidth = 'initial';
            }
        </script>
    </body>

    </html>                    
    ```

    **输出:**

    *   点击按钮前:
        ![initial-after](img/5f8f456f3b9488bf7e58b4cc436e5451.png)
    *   点击按钮后:
        ![initial-after](img/c836f1eaae86516f94c9a8ad7e446bab.png)
*   **inherit:** This inherits the property from its parent.
    **Example:**

    ```html
    <!DOCTYPE html>
    <html>

    <head>
        <title>
            DOM Style outlineWidth property
        </title>

        <style>
            #parent {
                padding: 10px;
                outline-style: dashed;

                /* Set the outlineWidth of
                parent element */
                outline-width: 5px;
            }
            .elem {
                outline-style: dotted;
            }
        </style>
    </head>

    <body>
        <h1 style="color: green">
            GeeksforGeeks
        </h1>

        <b>DOM Style OutlineWidth</b>

        <br><br>

        <div id="parent">
            <p class="elem">
                GeeksforGeeks is a computer science portal
                with a huge variety of well written and 
                explained computer science and programming
                articles, quizzes and interview questions.
                The portal also has dedicated GATE preparation
                and competitive programming sections.
            </p>
        </div>

        <br>

        <button onclick="changeWidth()">
            Change outlineWidth
        </button>

        <!-- Script to change the outline width -->
        <script>
            function changeWidth() {
                elem = document.querySelector('.elem');
                elem.style.outlineWidth = 'inherit';
            }
        </script>
    </body>

    </html>                    
    ```

    **输出:**

    *   点击按钮前:
        ![inherit-before](img/65f4db1ae5d3b75da524264474fcb078.png)
    *   点击按钮后:
        ![inherit-after](img/8699fb87795227abe1c2d377585353c5.png)

    **支持的浏览器:**以下列出了*DOM Style outlineidth 属性*支持的浏览器:

    *   谷歌 Chrome
    *   微软公司出品的 web 浏览器
    *   火狐浏览器
    *   歌剧
    *   苹果 Safari