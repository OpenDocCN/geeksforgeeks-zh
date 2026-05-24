# CSS |左边距属性

> 原文:[https://www.geeksforgeeks.org/css-margin-left-property/](https://www.geeksforgeeks.org/css-margin-left-property/)

CSS 中的左边距属性用于设置所需元素左边距的宽度。允许该属性的负值。

*   当希望边距远离其邻居时，使用正值。
*   当需要将边距放得更近时，使用负值。

**语法**:

```html
margin-left: length|auto|initial|inherit;
```

**默认值:**其默认值为 0。

**属性值**:

*   **length :** Sets a fixed value defined in px, cm, pt. Negative values as mentioned earlier are allowed. 0 px is the default value.

    ```html
    margin-left: 15px;

    ```

    **例 1** :

    ```html
    <html>
       <head>
          <title>
             CSS | margin-left Property
          </title>
       </head>

       <body>
          <p style = "margin-left:15px; border-style:solid ; 
                      border-color:black;">
             This paragraph has 15px margin .
          </p>
       </body>
    </html>
    ```

    **例 2** :

    ```html
    <html>
       <head>
          <title>
             CSS | margin-left Property
          </title>
       </head>

       <body>
          <p style = "margin-left:20%; border-style:solid ; 
                      border-color:black;">
             This paragraph has 20% margin .
          </p>
       </body>
    </html>
    ```

*   **auto :**It is used when it is desired that the browser determines the width of the left margin.

    ```html
    margin-left: auto;

    ```

    **例**:

    ```html
    <html>
       <head>
          <title>
             CSS | margin-left Property
          </title>
       </head>

       <body>
          <p style = "margin-left:auto; border-style:solid ; 
                      border-color:black;">
             This paragraph has auto margin .
          </p>
       </body>
    </html>
    ```

*   **initial :**It is used to set the value of the margin-left property to its default value.

    ```html
    margin-left: initial;

    ```

    **例**:

    ```html
    <html>
       <head>
          <title>
             CSS | margin-left Property
          </title>
       </head>

       <body>
          <p style = "margin-left:initial; border-style:solid ; 
                      border-color:black;">
             This paragraph has initial margin .
          </p>
       </body>
    </html>
    ```

*   **inherit :**It is used when it is desired that the element inherit the margin-left property of its parent as its own.

    ```html
    margin-left: inherit; 

    ```

    **例 1** :

    ```html
    <html>
       <head>
          <title>
             CSS | margin-left Property
          </title>
       </head>

       <body>
          <div style="margin-left:50px;">
          <p style = "margin-left:inherit; border-style:solid ; 
                      border-color:black;">
             This paragraph has auto margin .
          </p>
          </div>
       </body>
    </html>
    ```

    **例 2** :

    ```html
    <html>
       <head>
          <title>
             CSS | margin-left Property
          </title>
       </head>

       <body>
          <p style = "margin-left:auto; border-style:solid ; 
                      border-color:black;">
             This paragraph has auto margin .
          </p>

          <p style = "margin-left:10px; border-style:solid ; 
                      border-color:black;">
             This paragraph has 10px margin.
          </p>
          <br>

          <p style = "margin-left:5%;border-style:solid; 
                      border-color: black;">
             This paragraph has 5% margin.
          </p>
          <br>

          <p style = "margin-left:15px; border-style:solid;
                      border-color: black;">
             This text has an margin of 15px.
          </p>
          <br><br>   

          <p style = "margin-left:initial;border-style:solid;
                      border-color: black;">
             This text has a margin of default
             typeset by initial
          </p>   
       </body>
    </html> 
    ```

**支持的浏览器**:*左边距属性*支持的浏览器如下:

*   谷歌 Chrome 1.0
*   Internet Explorer 6.0
*   歌剧 3.5
*   Firefox1.0
*   Safari 1.0