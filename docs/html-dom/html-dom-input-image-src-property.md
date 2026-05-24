# HTML | DOM 输入图像 src 属性

> 原文:[https://www . geesforgeks . org/html-DOM-input-image-src-property/](https://www.geeksforgeeks.org/html-dom-input-image-src-property/)

**输入图像 src 属性**用于设置或返回输入图像的 src 属性值。 **src 属性**用于指定要用作提交按钮的图像的网址。

**语法:**

*   它返回 src 属性。

    ```html
    imageObject.src
    ```

*   它设置 src 属性。

    ```html
    imageObject.src
    ```

**属性值:**包含单个值 **URL** ，指定源图像的链接。下面列出了两种类型的网址链接:

*   **绝对 URL:** 指向另一个网页。
*   **相对 URL:** 指向同一网页的其他文件。

**返回值:**返回一个字符串值，代表输入图像的网址。

**示例-1:** 本示例返回输入图像 src 属性。

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        HTML DOM Input Image src Property
    </title>
</head>

<body style="text-align:center;">

    <h1 style="color:green;"> 
            GeeksForGeeks 
        </h1>

    <h2>DOM Input Image src Property</h2>
    <button onclick="my_geek()">
        <input id="myImage" 
               value="myGeeks"
               type="image"
               src=
"https://media.geeksforgeeks.org/wp-content/uploads/gfg-40.png" 
               alt="Submit" 
               formaction="#" 
               formtarget="#" 
               formenctype="text/plain" 
               width="48"
               height="48">
    </button>
    <h2 id="Geek_h" 
        style="color:green;"> 

        </h2>
    <script>
        function my_geek() {

            // Return formTarget, formEnctype and formAction. 
            var txt = document.getElementById(
                "myImage").src;
            document.getElementById(
                "Geek_h").innerHTML = txt;
        }
    </script>
</body>

</html>
```

**输出:**
**点击按钮前:**
![](img/56ef43be15721d3d5db58bfc7f7dd909.png)

**点击按钮后:**
![](img/005736046f0f004f69c7acbc17837354.png)

**示例-2** 本示例设置输入图像 src 属性。

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        HTML DOM Input Image src Property
    </title>
</head>

<body style="text-align:center;">

    <h1 style="color:green;"> 
            GeeksForGeeks 
        </h1>

    <h2>DOM Input Image src Property</h2>
    <button onclick="my_geek()">
        <input id="myImage" 
               value="myGeeks"
               type="image"
               src=
"https://media.geeksforgeeks.org/wp-content/uploads/gfg-40.png"
               alt="Submit" 
               formaction="#" 
               a formtarget="#" 
               formenctype="text/plain" 
               width="48"
               height="48">
    </button>
    <h2 id="Geek_h" style="color:green;"> 

        </h2>
    <script>
        function my_geek() {

            // Return formTarget, formEnctype and formAction. 
            var txt = document.getElementById(
                "myImage").src =
"https://media.geeksforgeeks.org/wp-content/uploads/20190506164011/logo3.png";

            document.getElementById("Geek_h").innerHTML = txt;
        }
    </script>
</body>

</html>
```

**输出:**
**点击按钮前:**
![](img/56ef43be15721d3d5db58bfc7f7dd909.png)
**点击按钮后:**
![](img/23355456d7c41cdd2f00ad96f2b4f2b5.png)

**支持的浏览器:****DOM 输入图像 src 属性**支持的浏览器如下:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   苹果 Safari
*   歌剧