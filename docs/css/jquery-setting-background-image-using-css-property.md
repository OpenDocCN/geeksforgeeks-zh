# JQuery |使用 CSS 属性设置背景图像

> 原文:[https://www . geesforgeks . org/jquery-设置-背景-图像-使用-css-property/](https://www.geeksforgeeks.org/jquery-setting-background-image-using-css-property/)

要使用 CSS 属性设置背景图像，我们使用**。jQuery 的 css()方法**。要理解例子首先要理解方法。

**JQuery。css()方法:**
此方法**为指定元素设置** / **返回**一个或多个样式属性。

**语法:**

*   **返回一个 CSS 属性:**

```html
$(selector).css("propertyname");

```

*   **Set a CSS property:**

    ```html
    $(selector).css("propertyname", "value");

    ```

    **示例-1:** 在本例中，使用 JQuery 的**由**背景图像**属性设置背景图像。css()方法**。

    ```html
    <!DOCTYPE html>
    <html>

    <head>
        <title>
            JQuery |
          Setting background-image using CSS property.
        </title>
        <style>
            #div {
                background-repeat: no-repeat;
                margin-left: 120px;
            }
        </style>
        <script src=
    "https://ajax.googleapis.com/ajax/libs/jquery/3.4.0/jquery.min.js">
        </script>

    </head>

    <body style="text-align: center;">
        <div id="div">
            <h1 style="color: green;">  
                     GeeksForGeeks  
                </h1>
            <p>
                This is text of the div box, .
            </p>
            <br>
            <button>
                click to set
            </button>
        </div>
        <br>
        <br>
        <script>
            $('button').on('click', function() {
                $('#div')
                    .css('background-image',
                        'url(' + 
    'https://media.geeksforgeeks.org/wp-content/uploads/20190515121004/gfgbg1.png'
                         + ')'
                    );
                $('h1').css('color', 'black');
            });
        </script>
    </body>

    </html>
    ```

    **输出:**

    *   **点击按钮前:**
        ![](img/be3001c89b90c1e3d80eb6ef11891a3f.png)
    *   **点击按钮后:**
        ![](img/2246f5b5db3f3d609ac0fcf695a19119.png)

    **示例-2:** 在本例中，背景图像和背景重复属性由**背景**属性使用 JQuery 的**设置。css()方法**。

    ```html
    <!DOCTYPE html>
    <html>

    <head>
        <title>
            JQuery 
          | Setting background-image using CSS property.
        </title>
        <style>
            #div {
                margin-left: 120px;
            }
        </style>
        <script src=
    "https://ajax.googleapis.com/ajax/libs/jquery/3.4.0/jquery.min.js">
        </script>

    </head>

    <body style="text-align: center;">
        <div id="div">
            <h1 style="color: green;">  
                    GeeksForGeeks  
                </h1>
            <p>
                This is text of the div box, .
            </p>
            <br>
            <button>
                click to set
            </button>
        </div>
        <br>
        <br>
        <script>
            $('button').on('click', function() {
                $('#div')
                    .css('background', 'url(' + 
    'https://media.geeksforgeeks.org/wp- 
                    content / uploads / 20190515121004 / gfgbg1.png '+ '
                        ) no - repeat '
            ); $('h1').css('color', 'black');
            });
        </script>
    </body>

    </html>
    ```

    **输出:**

    *   **点击按钮前:**
        ![](img/be3001c89b90c1e3d80eb6ef11891a3f.png)
    *   **点击按钮后:**
        ![](img/2246f5b5db3f3d609ac0fcf695a19119.png)