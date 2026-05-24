# CSS |边框-顶宽属性

> 原文:[https://www . geesforgeks . org/CSS-border-top-width-property/](https://www.geeksforgeeks.org/css-border-top-width-property/)

CSS 中的边框顶部宽度属性用于设置元素顶部边框的特定宽度。在使用边框顶部宽度属性之前，元素使用边框顶部样式或边框样式属性。

**默认值:**

*   媒介

**语法:**

```html
border-top-width: length|thin|medium|thick|initial|inherit;
```

**属性值:**边框顶部宽度属性值如下:

*   **长度:**用于设置边框的宽度。它不取负值。
*   **细:**用于在元素顶部设置细边框。
*   **中:**用于设置中等大小的上边框。这是默认值。
*   **粗:**用于设置粗顶边框。
*   **初始值:**用于将边框顶宽设置为默认值。
*   **inherit:** 此属性从其父级继承。

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>
    <head>
        <title>
            border-top-width property
        </title>

        <style>
            #thin {
                border-color: green;
                border-top-style: solid;
                border-top-width: thin;
            }
            #medium {
                border-color: green;
                border-top-style: solid;
                border-top-width: medium;
            }
            #thick {
                border-color: green;
                border-top-style: solid;
                border-top-width:thick;
            }
            #length {
                border-color: green;
                border-top-style: solid;
                border-top-width: 20px;
            }
            #initial {
                border-color: green;
                border-top-style: solid;
                border-top-width: initial;
            }
        </style>
    </head>

    <body style = "text-align:center">

        <h1 style = "color:green">GeeksforGeeks</h1>

        <h3>border-top-width property</h3>

        <div id="thin">
            border-top-width: thin;
        </div><br><br>

        <div id="medium">
            border-top-width: medium;
        </div><br><br>

        <div id="thick">
            border-top-width: thick;
        </div><br><br>

        <div id="length">
            border-top-width: length;
        </div><br><br>

        <div id="initial">
            border-top-width: initial;
        </div>
    </body>
</html>                                
```

**输出:**

![](img/0070e95eb58095805214de1e17ad991b.png)

**浏览器支持:***边框顶宽*属性支持的浏览器如下:

*   谷歌 Chrome 1.0
*   Internet Explorer 4.0
*   歌剧 3.5
*   Safari 1.0
*   Firefox 1.0