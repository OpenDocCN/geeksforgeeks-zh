# HTML | hs space 属性

> 原文:[https://www.geeksforgeeks.org/html-object-hspace-attribute/](https://www.geeksforgeeks.org/html-object-hspace-attribute/)

**HTML <对象> hspace 属性**用于指定对象左右两侧的空格数。

**语法:**

```html
<object hspace="pixels"> 
```

**属性:**

*   **像素:**它以像素为单位指定对象左右两侧的空白数量。

**注意:**HTML 5 中不支持 **<对象>** 空间属性。

下面的例子说明了 HTML 中的 **<对象>空间属性**:

**示例 1:** 在此示例中，对象的两侧都有 50px 的边距。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        HTML object hspace Attribute
    </title>
</head>

<body>
    <center>

        <h1 style="color:green">GeeksforGeeks</h1>
        <h4>
            HTML <object>hspace Attribute
        </h4>
        <br>

        <object data=
"https://www.geeksforgeeks.org/wp-content/uploads/Geek_logi_-low_res.png"
                width="350px" height="150px" hspace="50">
            GeeksforGeeks
        </object>
    </center>
</body>

</html>
```

**输出:**

![](img/5ddd408bd950f634c8e0fc8959a26b07.png)

**例 2:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        HTML object hspace Attribute
    </title>
</head>

<body>
    <center>

        <h1 style="color:green">GeeksforGeeks</h1>
        <h4>
         HTML <object>hspace Attribute
        </h4>
    </center>
    <br>

    <div><b>With 50px hspace:</b>
        <object hspace="50">
            GeeksforGeeks
        </object>
        <object hspace="50">
            A Computer Science Portal
        </object>
    </div>

    <br><br>

    <div><b>Without hspace:</b>
        <object>
            GeeksforGeeks
        </object>

        <object>
            A Computer Science Portal
        </object>
    </div>

</body>

</html>
```

**输出:**

![](img/6cad99574fdaf682257a7b349db97fae.png)

**支持的浏览器:**T2 HTML<对象> hspace 属性支持的浏览器如下:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   歌剧
*   旅行队