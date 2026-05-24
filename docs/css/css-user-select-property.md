# CSS |用户选择属性

> 原文:[https://www.geeksforgeeks.org/css-user-select-property/](https://www.geeksforgeeks.org/css-user-select-property/)

此属性用于指定用户是否可以选择文本。
**注意:**双击某些文本将被选中/高亮显示，但该属性可用于防止这种情况。

**语法:**

```html
user-select: auto|none|text|all;
```

**默认值:自动**

**房产价值:**

**自动:**有默认值，即用户可以选择文本。
**语法:**

```html
user-select: auto;
```

**例:**

## 超文本标记语言

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

**输出:**

![](img/b102ae2d661a462a2a48b34f526ff587.png)

**无:**用于阻止用户选择文本，表示用户无法自行选择文本。
**语法:**

```html
user-select: none;
```

**例:**

## 超文本标记语言

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

**输出:**

![](img/be1e9fb9b4f18c73d9171ff2abf23b28.png)

**文本:**该属性允许用户选择文本。它不提供阻止用户选择文本。
**语法:**

```html
user-select: text;
```

**例:**

## 超文本标记语言

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

**输出:**

![](img/c94f59387f98001b50cc6b0ee08a2b93.png)

**all:** 用于鼠标一击选择文本，而不是双击。
**语法:**

```html
user-select: all;
```

**例:**

## 超文本标记语言

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

**输出:**

![](img/91a11899edefa8e07f23fb5d94595503.png)

**支持的浏览器:**用户选择属性支持的浏览器如下:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   歌剧
*   旅行队