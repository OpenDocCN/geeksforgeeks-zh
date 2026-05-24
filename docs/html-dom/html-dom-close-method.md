# HTML | DOM close()方法

> 原文:[https://www.geeksforgeeks.org/html-dom-close-method/](https://www.geeksforgeeks.org/html-dom-close-method/)

**DOM close()方法**用于关闭输出流。它用来表示在窗户上书写的完成。close()方法不需要任何参数。

**语法:**

```html
document.close()
```

**例 1:**

```html
<!DOCTYPE html>
<html>
    <head>
        <title>DOM close Method</title>
        <style>
            h1, h2{
            color:green;
        }
        body {
            text-align:center;
        }
        </style>
    </head>
    <body>
        <h1>GeeksForGeeks</h1>
        <h2>DOM close() Method</h2>
        <button onclick="geeks()">Submit</button>
        <script>

            // This function is called on submit, it opens
            // a stream, write "PRACTICE" and then closes
            // the stream.
            function geeks() {
                document.open();
                document.write("<h1>PRACTICE</h1>");
                document.close();
            }
        </script>
    </body>
</html>                    
```

**输出:**
![](img/92e637236d90305eb5e1d9b0e30bf26d.png)

**示例 2:** 本示例使用 window.close 方法在新窗口中显示输出。

```html
<!DOCTYPE html>
<html>
    <head>
        <style>
            h1, h2 {
                color:green;
            }
            body {
                text-align:center;
            }
        </style>
    </head>
    <body>
        <h1>GeeksForGeeks</h1>
        <h2>DOM close() Method</h2>
        <button onclick="geeks()">Submit</button>
        <script>

            // This function is called on submit, it opens
            // a new window and a stream, write "PRACTICE" and 
            // then closes the stream.
            function geeks() {
                var gfg = window.open();
                gfg.document.open();
                gfg.document.write("<h1>PRACTICE</h1>");
                gfg.document.close();
            }
        </script>
    </body>
</html>                    
```

**输出:**
![](img/03b670eba8704546ffb117b105af8cf6.png)

**支持的浏览器:**DOM close()方法支持的浏览器如下:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   歌剧
*   旅行队