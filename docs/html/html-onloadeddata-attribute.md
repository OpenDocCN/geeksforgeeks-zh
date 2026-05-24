# HTML 加载数据属性

> 原文:[https://www.geeksforgeeks.org/html-onloadeddata-attribute/](https://www.geeksforgeeks.org/html-onloadeddata-attribute/)

**HTML onloadeddata 属性**是一个事件属性，当当前帧数据被加载，但下一帧的数据不足以播放音频/视频时，就会发生该事件属性。

**语法:**

```html
<element onloadeddata="myScript">
```

**属性值:**该属性包含单值脚本，在 onloadeddata 事件属性调用时工作。该属性由<音频>和<视频>标签支持。

**例 1:**

```html
<!DOCTYPE html>
<html>
    <head>
        <title>
            HTML onloadeddata Attribute
        </title>
    </head>

    <body>
        <center>
            <h1 style="color: green;">
                GeeksforGeeks
            </h1>
            <h2>
                HTML onloadeddata Attribute
            </h2>
            <audio controls id="audioId" 
                   onloadeddata="GFGfun()">
                <source src=
"https://media.geeksforgeeks.org/wp-content/uploads/20190625153922/frog.mp3"
                        type="audio/mpeg" />
            </audio>

            <script>
                function GFGFun() {
                    alert(
                "Browser has loaded the current frame");
                }
            </script>
        </center>
    </body>
</html>
```

**输出:**

![](img/3ef0aa006dbd32bc4a1d8150b9a89ec5.png)

**之后:**

![](img/f18a4faa90767edb2ebc20bdf11b6a67.png)

**例 2:**

```html
<!DOCTYPE html>
<html>
    <head>
        <title>
            HTML onloadeddata Attribute
        </title>
    </head>

    <body>
        <center>
            <h1 style="color: green;">
                GeeksforGeeks
            </h1>
            <h2>
                HTML onloadeddata Attribute
            </h2>
            <video controls id="VideoId" 
                   width="320" 
                   height="240"
                   onloadeddata="GFGfun()">
              <source src=
"https://media.geeksforgeeks.org/wp-content/uploads/20190401140735/g4g2.mp4" 
                      type="video/mp4" />
          </video>

         <script>
          function GFGFun() {
            alert("Browser has loaded the current frame");
          }
            </script>
        </center>
    </body>
</html>
```

**输出:**

![](img/6b63dbda8e52dd04207078e2f3fd263f.png)

**之后:**

![](img/646ae352933e3569ef1a249f9b19cc63.png)

**支持的浏览器:**

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   苹果 Safari
*   歌剧