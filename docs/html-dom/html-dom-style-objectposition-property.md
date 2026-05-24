# HTML | DOM 样式对象位置属性

> 原文:[https://www . geesforgeks . org/html-DOM-style-object position-property/](https://www.geeksforgeeks.org/html-dom-style-objectposition-property/)

DOM Style **objectPosition** 属性用于**设置**或**返回** *图像或视频在自己的内容框中的位置。*

**语法:**

*   它返回 objectPosition 属性。

    ```html
    object.style.objectPosition
    ```

*   它用于设置 objectPosition 属性。

    ```html
    object.style.objectPosition = "position|initial|inherit"
    ```

**属性值:**

*   **position:** This is used to specify the position of the image or video in terms of either length values or strings (left, right and center).

    **示例-1:**

    ```html
    <!DOCTYPE html>
    <html>

    <head>
        <title>
            DOM Style objectPosition Property
        </title>
        <style>
            .content {
                border: 1px solid;
                object-fit: cover;
                height: 250px;
                width: 500px;
            }
        </style>
    </head>

    <body>
        <h1 style="color: green">
          GeeksforGeeks
        </h1>
        <b>
          DOM Style objectPosition Property
        </b>
        <p>
          The objectPosition property 
          specify how an image or video 
          should be positioned in its content box.
        </p>
        <img src=
    "https://media.geeksforgeeks.org/wp-content/uploads/20190311222622/sample-image.png" 
             height="800" 
             width="800" 
             class="content" />

        <button onclick="setObjectPosition()">
            Change resize
        </button>

        <!-- Script to set objectPosition to 50% 100% -->
        <script>
            function setObjectPosition() {
                elem = document.querySelector('.content');
                elem.style.objectPosition = '75% 100%';
            }
        </script>
    </body>

    </html>
    ```

    **输出:**

    *   Before clicking the button:

        ![position-before](img/f231333983031723ac59a3ba7b8e049c.png)

    *   After clicking the button:

        ![position-after](img/1b465b7cb760e15f9cc77f3f82a0af67.png)

*   **initial:** This is used to set this property to its default value.

    **示例-2:**

    ```html
    <!DOCTYPE html>
    <html>

    <head>
        <title>
            DOM Style objectPosition Property
        </title>
        <style>
            .content {
                border: 1px solid;
                object-fit: cover;
                height: 250px;
                width: 500px;
                object-position: 50% 100%;
            }
        </style>
    </head>

    <body>
        <h1 style="color: green">
          GeeksforGeeks
        </h1>
        <b>
          DOM Style objectPosition Property
        </b>
        <p>
            The objectPosition property specify 
          how an image or video should be
          positioned in its content box.
        </p>
        <img src=
    "https://media.geeksforgeeks.org/wp-content/uploads/20190311222622/sample-image.png"
             height="800"
             width="800"
             class="content" />

        <button onclick="setObjectPosition()">
            Change resize
        </button>

        <!-- Script to set objectPosition to initial -->
        <script>
            function setObjectPosition() {
                elem = document.querySelector('.content');
                elem.style.objectPosition = 'initial';
            }
        </script>
    </body>

    </html>
    ```

    **输出:**

    *   Before clicking the button:

        ![initial-before](img/31da77fe98dcbb8d7350c649c69da0b7.png)

    *   After clicking the button:

        ![initial-after](img/d3a65ab6ab00eb18949a755e3112b5c0.png)

        *   **inherit:** This inherits the property from its parent.

    **示例-3:**

    ```html
    <!DOCTYPE html>
    <html>

    <head>
        <title>
            DOM Style objectPosition Property
        </title>
        <style>
            #parent {
                object-position: 50% 100%;
            }

            .content {
                border: 1px solid;
                object-fit: cover;
                height: 250px;
                width: 500px;
            }
        </style>
    </head>

    <body>
        <h1 style="color: green">
          GeeksforGeeks
        </h1>
        <b>
          DOM Style objectPosition Property
        </b>
        <p>
            The objectPosition property specify how an 
          image or video should be positioned in its content box.
        </p>
        <div id="parent">
            <img src=
    "https://media.geeksforgeeks.org/wp-content/uploads/20190311222622/sample-image.png" 
                 height="800"
                 width="800" 
                 class="content" />
        </div>

        <button onclick="setObjectPosition()">
            Change resize
        </button>

        <!-- Script to set objectPosition to inherit -->
        <script>
            function setObjectPosition() {
                elem = document.querySelector('.content');
                elem.style.objectPosition = 'inherit';
            }
        </script>
    </body>

    </html>
    ```

    **输出:**

    *   Before clicking the button:

        ![inherit-before](img/29b1983ff412702ef6e3e1c1a1ba0f1b.png)

    *   After clicking the button:

        ![inherit-after](img/df45ec2b14c4d85ee575271a069d044c.png)

**支持的浏览器:**由*对象位置*属性支持的浏览器如下:

*   谷歌 Chrome 31.0
*   Internet Explorer 16.0
*   Firefox 36.0
*   Opera 19.0
*   苹果 Safari 10.1