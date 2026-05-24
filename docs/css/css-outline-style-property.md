# CSS |轮廓样式属性

> 原文:[https://www.geeksforgeeks.org/css-outline-style-property/](https://www.geeksforgeeks.org/css-outline-style-property/)

CSS 中的 outline-style 属性用于设置元素轮廓的外观。元素的轮廓和边框相似，但不相同。轮廓不占用空间，并且绘制在元素的边框之外。此外，默认情况下，轮廓是围绕元素的所有四个边绘制的，无法更改这一点。

**语法:**

```html
outline-style: auto|none|dotted|dashed|solid|double|groove|ridge|
inset|outset|initial|inherit;
```

**属性值:**

*   **auto:** It sets the outline of an elements through the browser.

    **语法:**

    ```html
    outline-style: auto;
    ```

    **示例:**

    ```html
    <!DOCTYPE html>
    <html>
        <head>
            <title>
                CSS outline-style property
            </title>

            <!-- Internal CSS Style Sheet -->
            <style>
                h1 {
                    color: green;
                    text-align: center;

                    /* CSS Property for outline-style */ 
                    outline-style: auto;
                }
            </style>

        </head>

        <body>
            <!-- outline-style: auto;-->
            <h1>GeeksForGeeks</h1>
        </body>
    </html>                    
    ```

    **输出:**
    ![CSS Property | outline-style-auto](img/b633260de1122584f0fbeee792e4d6ea.png)

*   **none:** It is the default value and it sets the outline width to zero. Hence, it is not visible.

    **语法:**

    ```html
    outline-style: none;
    ```

    **示例:**

    ```html
    <!DOCTYPE html>
    <html>
        <head>
            <title>
                CSS outline-style property
            </title>

            <!-- Internal CSS Style Sheet -->
            <style>
                h1 {
                    color: green;
                    text-align: center;

                    /* CSS Property for outline-style */ 
                    outline-style: none;
                }
            </style>

        </head>

        <body>

            <!-- outline-style: none;-->
            <h1>GeeksForGeeks</h1>
        </body>
    </html>                    
    ```

    **输出:**
    ![CSS Property | outline-style-none](img/159c5b7981b69fd12636bf0b4e97911b.png)

*   **dotted:** It is used to set a series of dots around the element as outline.

    **语法:**

    ```html
    outline-style: dotted;
    ```

    **示例:**

    ```html
    <!DOCTYPE html>
    <html>
        <head>
            <title>
                CSS outline-style property
            </title>

            <!-- Internal CSS Style Sheet -->
            <style>
                h1 {
                    color: green;
                    text-align: center;

                    /* CSS Property for outline-style */ 
                    outline-style: dotted;
                }
            </style>

        </head>

        <body>

            <!-- outline-style: dotted;-->
            <h1>GeeksForGeeks</h1>
        </body>
    </html>                    
    ```

    **输出:**
    ![CSS Property | outline-style-dotted](img/c83dcb56cb1685ed6949da908b637bc4.png)

*   **dashed:** It is used to set a series of dashed line segment around the element as outline.

    **语法:**

    ```html
    outline-style: dashed;
    ```

    **示例:**

    ```html
    <!DOCTYPE html>
    <html>
        <head>
            <title>
                CSS outline-style property
            </title>

            <!-- Internal CSS Style Sheet -->
            <style>
                h1 {
                    color: green;
                    text-align: center;

                    /* CSS Property for outline-style */ 
                    outline-style: dashed;
                }
            </style>

        </head>

        <body>

            <!-- outline-style: dashed;-->
            <h1>GeeksForGeeks</h1>
        </body>
    </html>                    
    ```

    **输出:**
    ![CSS Property | outline-style-dashed](img/fa692c8e0228c97f76768d7bfd8bc028.png)

*   **solid:** It is used to set solid line segment around the element as outline.

    **语法:**

    ```html
    outline-style: solid;
    ```

    **示例:**

    ```html
    <!DOCTYPE html>
    <html>
      <head>
        <title>CSS outline-style property</title>

        <!-- Internal CSS Style Sheet -->
        <style>
          h1{
            color: green;
            text-align: center;

            /* CSS Property for outline-style */ 
            outline-style: solid;
          }
        </style>

      </head>

      <body>
          <!-- outline-style: solid;-->
          <h1>GeeksForGeeks</h1>
      </body>

    </html>
    ```

    **输出:**
    ![CSS Property | outline-style-solid](img/4de8e98db9d119e72d5f0c361b28f071.png)

*   **double:** It sets a doubled line segments around the element as outline. The width of the outline is equal to the sum of width of the individual line segments and space between them.

    **语法:**

    ```html
    outline-style: double;
    ```

    **示例:**

    ```html
    <!DOCTYPE html>
    <html>
      <head>
        <title>CSS outline-style property</title>

        <!-- Internal CSS Style Sheet -->
        <style>
          h1{
            color: green;
            text-align: center;

            /* CSS Property for outline-style */ 
            outline-style: double;
          }
        </style>

      </head>

      <body>
          <!-- outline-style: double;-->
          <h1>GeeksForGeeks</h1>
      </body>

    </html>
    ```

    **输出:**
    ![CSS Property | outline-style-double](img/727123a4919b87585218802c62e8ec16.png)

*   **groove:** It sets grooved line segments around the element as the outline, which makes feel that it is carved.

    **语法:**

    ```html
    outline-style: groove;
    ```

    **示例:**

    ```html
    <!DOCTYPE html>
    <html>
        <head>
            <title>
                CSS outline-style property
            </title>

            <!-- Internal CSS Style Sheet -->
            <style>
                h1 {
                    color: green;
                    text-align: center;
                    outline-width: 8px;

                    /* CSS Property for outline-style */ 
                    outline-style: groove;
                }
            </style>

        </head>

        <body>

            <!-- outline-style: groove;-->
            <h1>GeeksForGeeks</h1>
        </body>
    </html>                    
    ```

    **输出:**
    ![CSS Property | outline-style-groove](img/a2ba33bf68a2b94b5ceb2b0b707cd384.png)

*   **ridge:** It sets ridged line segments around the element as outline, which makes feel that it is extruding. It is opposite to that of a groove.

    **语法:**

    ```html
    outline-style: ridge;
    ```

    **示例:**

    ```html
    <!DOCTYPE html>
    <html>
        <head>
            <title>
                CSS outline-style property
            </title>

            <!-- Internal CSS Style Sheet -->
            <style>
                h1 {
                    color: green;
                    text-align: center;
                    outline-width: 8px;

                    /* CSS Property for outline-style */ 
                    outline-style: ridge;
                }
            </style>
        </head>

        <body>

            <!-- outline-style: ridge;-->
            <h1>GeeksForGeeks</h1>
        </body>
    </html>                    
    ```

    **输出:**
    ![CSS Property | outline-style-ridge](img/f3bc0699f382be9af19de2af52908ac2.png)

*   **inset:** It sets embedded line segments around the element as the outline, which makes us feel that it is fixed in the display.

    **语法:**

    ```html
    outline-style: inset;
    ```

    **示例:**

    ```html
    <!DOCTYPE html>
    <html>
        <head>
            <title>
                CSS outline-style property
            </title>

            <!-- Internal CSS Style Sheet -->
            <style>
                h1 {
                    color: green;
                    text-align: center;
                    outline-width: 8px;

                    /* CSS Property for outline-style */ 
                    outline-style: inset;
                }
            </style>
        </head>

        <body>

            <!-- outline-style: inset;-->
            <h1>GeeksForGeeks</h1>
        </body>
    </html>                    
    ```

    **输出:**
    ![CSS Property | outline-style-inset](img/1890c2f4889d4d48fe7df74c29ec0685.png)

*   **outset:** It sets line segments around the element which appears to be coming out, as outline. It is opposite of inset.

    **语法:**

    ```html
    outline-style: outset;
    ```

    **示例:**

    ```html
    <!DOCTYPE html>
    <html>
        <head>
            <title>
                CSS outline-style property
            </title>

            <!-- Internal CSS Style Sheet -->
            <style>
                h1 {
                    color: green;
                    text-align: center;
                    outline-width: 8px;

                    /* CSS Property for outline-style */ 
                    outline-style: outset;
                }
            </style>
        </head>

        <body>

            <!-- outline-style: outset;-->
            <h1>GeeksForGeeks</h1>
        </body>
    </html>                    
    ```

    **输出:**
    ![CSS Property | outline-style-outset](img/d36fe8c2be424afab853f26ef1ad0154.png)

*   **initial:** It is used to set outline-style property to its default value. It sets the width of the outline to zero. Hence, the outline is not visible.

    **语法:**

    ```html
    outline-style: initial;
    ```

    **示例:**

    ```html
    <!DOCTYPE html>
    <html>
        <head>
            <title>
                CSS outline-style property
            </title>

            <!-- Internal CSS Style Sheet -->
            <style>
                h1 {
                    color: green;
                    text-align: center;
                    outline-width: 5px;
                    outline-color: black;

                    /* CSS Property for outline-style */
                    outline-style: initial;
                }
            </style>
        </head>

        <body>

            <!-- outline-style: initial;-->
            <h1>GeeksForGeeks</h1>
        </body>

    </html>                    
    ```

    **输出:**
    ![CSS Property | outline-style-initial](img/47a1743fbff501305d4fe893e8455f6f.png)

*   **inherit:** It makes the outline-style property to be inherited from its parent element.

    **语法:**

    ```html
    outline-style: inherit;
    ```

    **示例:**

    ```html
    <!DOCTYPE html>
    <html>
        <head>
            <title>
                CSS outline-style property
            </title>

            <!-- Internal CSS Style Sheet -->
            <style>
                * {
                    padding: 1px;
                }
                body {
                    outline-style: dashed;
                }
                h1 {
                    color: green;
                    text-align: center;
                    outline-width: 5px;
                    outline-color: black;

                    /* CSS Property for outline-style */
                    outline-style: inherit;
                }
            </style>
        </head>

        <body>

            <!-- outline-style: inherit;-->
            <h1>GeeksForGeeks</h1>
        </body>
    </html>                    
    ```

    **输出:**
    ![CSS Property | outline-style-inherit](img/a84287f5e192685bed7f3715e67e4884.png)

**支持的浏览器:***轮廓式*属性支持的浏览器如下:

*   谷歌 Chrome 1.o
*   Internet Explorer 8
*   Firefox 1.5
*   Opera 7.0
*   Safari 1.2