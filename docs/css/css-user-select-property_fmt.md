# CSS `user-select` 属性

> 原文：[https://www.geeksforgeeks.org/css-user-select-property/](https://www.geeksforgeeks.org/css-user-select-property/)

此属性用于指定用户是否可以选择文本。
**注意：** 双击某些文本将被选中/高亮显示，但该属性可用于防止这种情况。

**语法：**
```html
user-select: auto|none|text|all;
```

**默认值：** `auto`

**属性值：**

**`auto`：** 默认值，即用户可以选择文本。
**语法：**
```html
user-select: auto;
```

**示例：**
```html
<!DOCTYPE html>
<html>
    <head>
        <title>user-select property</title>
        <style>
            div {
                -webkit-user-select: auto;
                -moz-user-select: auto;
                -ms-user-select: auto;
                user-select: auto;
            }
            h1, h3 {
                color:green;
            }
            body {
                text-align:center;
            }
        </style>
    </head>
    <body>
        <h1>GeeksforGeeks</h1>
        <h3>user-select:auto;</h3>
        <div>
         GeeksforGeeks:
         A computer science portal for geeks
        </div>
    </body>
</html>
```

**输出：**
![](img/b102ae2d661a462a2a48b34f526ff587.png)

**`none`：** 用于阻止用户选择文本，表示用户无法自行选择文本。
**语法：**
```html
user-select: none;
```

**示例：**
```html
<!DOCTYPE html>
<html>
    <head>
        <title>user-select property</title>
        <style>
            div {
                -webkit-user-select: none;
                -moz-user-select: none;
                -ms-user-select: none;
                user-select: none;
            }
            h1, h3 {
                color:green;
            }
            body {
                text-align:center;
            }
        </style>
    </head>
    <body>
        <h1>GeeksforGeeks</h1>
        <h3>user-select:none;</h3>
        <div>
         GeeksforGeeks:
         A computer science portal for geeks
        </div>
    </body>
</html>
```

**输出：**
![](img/be1e9fb9b4f18c73d9171ff2abf23b28.png)

**`text`：** 该属性允许用户选择文本。它不提供阻止用户选择文本。
**语法：**
```html
user-select: text;
```

**示例：**
```html
<!DOCTYPE html>
<html>
    <head>
        <title>user-select property</title>
        <style>
            div {
                -webkit-user-select: text;
                -moz-user-select: text;
                -ms-user-select: text;
                user-select: text;
            }
            h1, h3 {
                color:green;
            }
            body {
                text-align:center;
            }
        </style>
    </head>
    <body>
        <h1>GeeksforGeeks</h1>
        <h3>user-select:text;</h3>
        <div>
         GeeksforGeeks:
         A computer science portal for geeks
        </div>
    </body>
</html>
```

**输出：**
![](img/c94f59387f98001b50cc6b0ee08a2b93.png)

**`all`：** 用于鼠标一击选择文本，而不是双击。
**语法：**
```html
user-select: all;
```

**示例：**
```html
<!DOCTYPE html>
<html>
    <head>
        <title>user-select property</title>
        <style>
            div {
                -webkit-user-select: all;
                -moz-user-select: all;
                -ms-user-select: all;
                user-select: all;
            }
            h1, h3 {
                color:green;
            }
            body {
                text-align:center;
            }
        </style>
    </head>
    <body>
        <h1>GeeksforGeeks</h1>
        <h3>user-select:text;</h3>
        <div>
         GeeksforGeeks:
         A computer science portal for geeks
       </div>
    </body>
</html>
```

**输出：**
![](img/91a11899edefa8e07f23fb5d94595503.png)

**支持的浏览器：** `user-select` 属性支持的浏览器如下：
*   `Google Chrome`
*   `Microsoft Edge`
*   `Firefox`
*   `Opera`
*   `Safari`