# HTML onprogress 属性

> 原文:[https://www.geeksforgeeks.org/html-onprogress-attribute/](https://www.geeksforgeeks.org/html-onprogress-attribute/)

HTML strong onprogress 属性是浏览器下载指定音频或视频时发生的事件属性。

语法:

```html
<element onprogress="myScript">
```

**属性值:**该属性包含单值脚本，在进行事件属性调用时工作。该属性由<音频>和<视频>标签支持。

**例 1:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>
    <head>
        <title>
            HTML onprogress Attribute
        </title>
    </head>

    <body>
        <center>
            <h1 style="color: green;">
                GeeksforGeks
            </h1>
            <h2>
                HTML onprogress Attribute
            </h2>

            <audio controls id="audioID"
                   onprogress="GFGfun()">
                <source src=
"https://media.geeksforgeeks.org/wp-content/uploads/20190625154540/hello-world.m4a"
                        type="audio/mpeg" />
            </audio>

            <script>
                function GFGfun() {
                    alert("audio progress");
                }
            </script>
        </center>
    </body>
</html>
```

**输出:**

![](img/737a1ed4b786935ab0de4fbd788feb01.png)

下载媒体后:

![](img/bf89f9cdd62c8ee9827ad28036fb7d5e.png)

例 2:

## 超文本标记语言

```html
<!DOCTYPE html>
<html>
    <head>
        <title>
            HTML onprogress Attribute
        </title>
    </head>

    <body>
        <center>
            <h1 style="color: green;">
                GeeksforGeks
            </h1>
            <h2>
                HTML onprogress Attribute
            </h2>

            <video controls id="vidID"
                   onprogress="GFGfun()"
                   width="320"
                   height="240">
                <source src=
"https://media.geeksforgeeks.org/wp-content/uploads/20190401140735/g4g2.mp4"
                        type="video/mp4" />
            </video>

            <script>
                function GFGfun() {
                    alert("Video progress");
                }
            </script>
        </center>
    </body>
</html>
```

**输出:**

![](img/76db0cb3ef2ea17da7dcd70c16fde3f7.png)

**之后:**

![](img/25ed821cf317563651c0f48f2bd38ef2.png)

**支持的浏览器:**

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   苹果 Safari
*   歌剧