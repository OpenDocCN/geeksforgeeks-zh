# HTML | DOM 输入图像高度属性

> 原文:[https://www . geesforgeks . org/html-DOM-input-image-height-property/](https://www.geeksforgeeks.org/html-dom-input-image-height-property/)

HTML DOM 中的**输入图像高度**用于设置或返回高度属性 **<的值。**

**语法:**

*   它返回高度属性。

    ```html
    imageObject.height
    ```

*   它设置高度属性。

    ```html
    imageObject.height = value;
    ```

**属性值:**包含以像素为单位指定图像高度的数值。

**返回值:**返回代表图像高度的数值。

**示例:**本示例返回输入图像高度属性。

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        HTML DOM Input Image height Property
    </title>
</head>

<body style="text-align:center;">

    <h1 style="color:green;"> 
            GeeksForGeeks 
        </h1>

    <h2>
      DOM Input Image height Property
  </h2>
    <button onclick="my_geek()">
        <input id="myImage"
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

            // Return formTarget,
            // formEnctype and formAction. 
            var txt = document.getElementById(
                "myImage").height;
            document.getElementById(
                "Geek_h").innerHTML = txt;
        }
    </script>
</body>

</html>
```

**输出:**
**点击按钮前:**
![](img/b485bdc88c12dc1e80ffec0e6a342da5.png)

**点击按钮后:**
![](img/55a7713e1f50585e64d79a58a2b01415.png)

**示例-2:** 本示例设置输入图像高度属性。

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        HTML DOM Input Image height Property
    </title>
</head>

<body style="text-align:center;">

    <h1 style="color:green;"> 
            GeeksForGeeks 
        </h1>

    <h2>DOM Input Image height Property</h2>
    <button onclick="my_geek()">
        <input id="myImage" 
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

            // Return formTarget, 
            // formEnctype and formAction. 
            var txt = document.getElementById(
                "myImage").height = 96;
            document.getElementById(
                "Geek_h").innerHTML = txt;
        }
    </script>
</body>

</html>
```

**输出:**
**点击按钮前:**
![](img/b485bdc88c12dc1e80ffec0e6a342da5.png)

**点击按钮后:**
![](img/1036afecb06050e034201906fce21415.png)

**支持的浏览器:****DOM 输入图像高度属性**支持的浏览器如下:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   苹果 Safari
*   歌剧