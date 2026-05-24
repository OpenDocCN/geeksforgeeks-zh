# HTML | DOM Samp 对象

> 原文:[https://www.geeksforgeeks.org/html-dom-samp-object/](https://www.geeksforgeeks.org/html-dom-samp-object/)

HTML DOM 中的 Samp 对象用来表示<samp>元素。使用 getElementById()方法可以访问<samp>元素。</samp></samp>

**语法:**

```html
document.getElementById("ID");
```

其中标识被分配给<samp>标签。</samp>

**例 1:**

```html
<!DOCTYPE html> 
<html> 
    <head> 
        <title>
            HTML DOM samp Object
        </title> 
    </head> 

    <body> 
        <h1>
            GeeksforGeeks
        </h1>

        <h2>
            HTML DOM Samp Object
        </h2>

        <samp id = "geeks">
            A computer science portal for Geeks
        </samp>

        <br><br>

        <button onclick = "myGeeks()">
            Submit
        </button>

        <script>
            function myGeeks() {
                var txt = document.getElementById("geeks");
                txt.style.color = "green";
                txt.style.fontSize = "16px";
            }
        </script>
    </body> 
</html>                              
```

**输出:**
**点击按钮前:**
![](img/c61feb7c9e9b73f23e21bc50e51bf2ce.png)
**点击按钮后:**
![](img/27d63fa5a44d5717157e784420f96984.png)

**示例 2:** 可以使用*文档.创建元素*方法创建采样对象。

```html
<!DOCTYPE html> 
<html> 
    <head> 
        <title>
            HTML DOM samp Object
        </title> 
    </head> 

    <body> 
        <h1>GeeksForGeeks</h1>

        <h2>DOM Samp Object</h2>

        <button onclick = "myGeeks()">
            Submit
        </button><br>

        <script>
            function myGeeks() {
                var cont = document.createElement("SAMP");
                var txt = document.createTextNode(
                           "A Computer SciencePortalForgeeks");

                cont.appendChild(txt);
                document.body.appendChild(cont);
            }
        </script>
    </body> 
</html>                             
```

**输出:**
**点击按钮前:**
![](img/72c1db4f1008c608311f9ec728e52755.png)
**点击按钮后:**
![](img/6cdccd216518cea18a12a9cff291ddad.png)

**支持的浏览器:***DOM Samp 对象*支持的浏览器如下:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   歌剧
*   旅行队