# HTML | DOM 样式文本转换属性

> 原文:[https://www . geesforgeks . org/html-DOM-style-text transform-property/](https://www.geeksforgeeks.org/html-dom-style-texttransform-property/)

HTML DOM 中的**样式**文本转换**属性**用于设置或返回文本的大写。它可用于使所需文本大写、小写或大写每个单词的第一个字符。

**语法:**

*   它返回 textTransform 属性。

    ```html
    object.style.textTransform
    ```

*   它用于设置文本转换属性。

    ```html
    object.style.textTransform = "capitalize|uppercase|lowercase|
    none|initial|inherit"
    ```

**返回值:**它返回一个字符串值，表示元素中文本的转换

**属性值:**

*   **capitalize:** This value capitalizes the first letter of every word of the text.

    **示例:**

    ```html
    <!DOCTYPE html>
    <html>

    <head>
        <title>
            DOM Style textTransform Property
        </title>
    </head>

    <body>
        <h1 style="color: green">
            GeeksforGeeks
        </h1>

        <b>DOM Style textTransform Property</b>

        <p>
            The textTransform property can be used
            to capitalize, uppercase or lowercase
            the text.
        </p>

        <p class="content">
            GeeksforGeeks is a computer science portal.
        </p>

        <button onclick="setTransform()">
            Change textTransform
        </button>

        <!-- Script to capitalize first character
            of each word -->
        <script>
            function setTransform() {
                elem = document.querySelector('.content');
                elem.style.textTransform = 'capitalize';
            }
        </script>
    </body>

    </html>                    
    ```

    **输出:**

    *   点击按钮前:
        ![capitalize-before](img/2ecbf04f0f85c9312f40748e260aa952.png)
    *   点击按钮后:
        ![capitalize-after](img/905ffc180843a5d04e2ed6b2fc7c15aa.png)
*   **uppercase:** This value transforms every letter of the text to uppercase.

    **示例:**

    ```html
    <!DOCTYPE html>
    <html>

    <head>
        <title>
            DOM Style textTransform Property
        </title>
    </head>

    <body>
        <h1 style="color: green">
            GeeksforGeeks
        </h1>

        <b>DOM Style textTransform Property</b>

        <p>
            The textTransform property can be used
            to capitalize, uppercase or lowercase
            the text.
        </p>

        <p class="content">
            GeeksforGeeks is a computer science portal.
        </p>

        <button onclick="setTransform()">
            Change textTransform
        </button>

        <!-- Script to capitalize each character -->
        <script>
            function setTransform() {
                elem = document.querySelector('.content');
                elem.style.textTransform = 'uppercase';
            }
        </script>
    </body>

    </html>                    
    ```

    **输出:**

    *   点击按钮前:
        ![uppercase-before](img/a5a69ac538a61f01fe079ca1d08bf595.png)
    *   点击按钮后:
        ![uppercase-after](img/2e699a4483c0d7f78efbbdd4befc3003.png)
*   **lowercase:** This value transforms every letter of the text to lowercase.

    **示例:**

    ```html
    <!DOCTYPE html>
    <html>

    <head>
        <title>
            DOM Style textTransform Property
        </title>
    </head>

    <body>
        <h1 style="color: green">
            GeeksforGeeks
        </h1>

        <b>DOM Style textTransform Property</b>

        <p>
            The textTransform property can be used to
            capitalize, uppercase or lowercase the text.
        </p>

        <p class="content">
            GeeksforGeeks Is A ComPuTer sCiEnce PortAL.
        </p>

        <button onclick="setTransform()">
            Change textTransform
        </button>

        <script>
            function setTransform() {
                elem = document.querySelector('.content');
                elem.style.textTransform = 'lowercase';
            }
        </script>
    </body>

    </html>            
    ```

    **输出:**

    *   点击按钮前:
        ![lowercase-before](img/cc553f2746541ab874ed72aed617450c.png)
    *   点击按钮后:
        ![lowercase-after](img/880b34858243095026ea8143770fe190.png)
*   **none:** It is the default value that specifies no transformation takes place.

    **示例:**

    ```html
    <!DOCTYPE html>
    <html>

    <head>
        <title>
            DOM Style textTransform Property
        </title>

        <style>
            .content {
                width: 500px;

                /* Set text-transform before to
                observe effect of 'none' */
                text-transform: capitalize;
            }
        </style>
    </head>

    <body>
        <h1 style="color: green">
            GeeksforGeeks
        </h1>

        <b>DOM Style textTransform Property</b>

        <p>
            The textTransform property can be used
            to capitalize, uppercase or lowercase
            the text.
        </p>

        <p class="content">
            GeeksforGeeks is a computer science portal.
        </p>

        <button onclick="setTransform()">
            Change textTransform
        </button>

        <!-- Script to convert lower case
            of each word -->
        <script>
            function setTransform() {
                elem = document.querySelector('.content');
                elem.style.textTransform = 'none';
            }
        </script>
    </body>

    </html>                    
    ```

    **输出:**

    *   点击按钮前:
        ![none-before](img/98fc537c3e385e993f0804aaa6cca53a.png)
    *   点击按钮后:
        ![none-after](img/7eca42ef8ea8803969ff072195d4ab18.png)
*   **initial:** This is used to set this property to its default value.

    **示例:**

    ```html
    <!DOCTYPE html>
    <html>

    <head>
        <title>
            DOM Style textTransform Property
        </title>

        <style>
            .content {
                width: 500px;

                /* Set text-transform before to
                observe effect of 'none' */
                text-transform: capitalize;
            }
        </style>
    </head>

    <body>
        <h1 style="color: green">
            GeeksforGeeks
        </h1>

        <b>DOM Style textTransform Property</b>

        <p>
            The textTransform property can be used
            to capitalize, uppercase or lowercase
            the text.
        </p>

        <p class="content">
            GeeksforGeeks is a computer science portal.
        </p>

        <button onclick="setTransform()">
            Change textTransform
        </button>

        <!-- Script to change lower case
            of each word -->
        <script>
            function setTransform() {
                elem = document.querySelector('.content');
                elem.style.textTransform = 'initial';
            }
        </script>
    </body>

    </html>                    
    ```

    **输出:**

    *   点击按钮前:
        ![initial-before](img/093bf1980284c50494ec23a4628d12e5.png)
    *   点击按钮后:
        ![initial-after](img/ca2744bdf0c069d9ec155a1afa41d5f0.png)
*   **inherit:** It inherits the property from its parent element.

    **示例:**

    ```html
    <!DOCTYPE html>
    <html>

    <head>
        <title>
            DOM Style textTransform Property
        </title>

        <style>
            #parent {

                /* Set text-transform of parent to
                observe effect of 'inherit' */
                text-transform: uppercase;
            }
            .content {
                width: 500px;

                /* Set text-transform to initial to prevent
                auto inheritance of parent */
                text-transform: initial;
            }
        </style>
    </head>

    <body>
        <h1 style="color: green">
            GeeksforGeeks
        </h1>

        <b>DOM Style textTransform Property</b>

        <p>
            The textTransform property can be used to 
            capitalize, uppercase or lowercase the text.
        </p>

        <div id="parent">
            <p class="content">
                GeeksforGeeks is a computer science portal.
            </p>
        </div>

        <button onclick="setTransform()">
            Change textTransform
        </button>

        <script>
            function setTransform() {
                elem = document.querySelector('.content');
                elem.style.textTransform = 'inherit';
            }
        </script>
    </body>

    </html>                    
    ```

    **输出:**

    *   点击按钮前:
        ![inherit-before](img/2cd0651c6c0ad57e3eb2ee603166325e.png)
    *   点击按钮后:
        ![inherit-after](img/a620728e3d40208bf8602b9c7c892139.png)

**支持的浏览器:***DOM Style textTransform 属性*支持的浏览器如下:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   歌剧
*   苹果 Safari