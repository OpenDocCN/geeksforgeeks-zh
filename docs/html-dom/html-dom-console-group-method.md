# HTML | DOM console.group()方法

> 原文:[https://www . geesforgeks . org/html-DOM-console-group-method/](https://www.geeksforgeeks.org/html-dom-console-group-method/)

HTML 中的 **console.group()** 方法用于在控制台中创建一组消息。它指示一个消息组的开始，调用 **console.group()** 方法后写入的所有消息都将写入消息组。标签作为可选参数发送给 console.group()方法。

**语法:**

```html
console.group( label )
```

**参数:**该方法接受单参数*标签*，该标签为可选，用于指定组的标签。

下面的程序用 HTML 说明了 console.group()方法:

**例 1:**

```html
<!DOCTYPE html>
<html>
    <head> 
        <title>DOM console.group() Method</title> 
        <style> 
            h1 { 
                color:green; 
            } 
            h2 {
                font-family: Impact;
            }
            body { 
                text-align:center; 
            } 
        </style> 
    </head>
    <body>
        <h1>GeeksforGeeks</h1> 
        <h2>DOM console.group() Method</h2> 

        <p>
         To view the message in the console
         press the F12 key on your keyboard.
        </p>
        <script>
            console.log("GeeksforGeeks offers the following courses :");
            console.group();
            console.log("1\. fork python");
            console.log("2\. fork cpp");
            console.log("3\. fork java");
            console.log("4\. Interview preparation");
        </script>
    </body>
</html>                    
```

**输出:**
![](img/0569530f27a7baf0a10c1305a9bbef7e.png)
**控制台视图:**
![](img/912840118a2aed51b5739338acf3e991.png)

**示例 2:** 在 console.group()方法中使用标签参数

```html
<!DOCTYPE html>
<html>
    <head> 
        <title>DOM console.group() Method</title> 
        <style> 
            h1 { 
                color:green; 
            } 
            h2 {
                font-family: Impact;
            }
            body { 
                text-align:center; 
            } 
        </style> 
    </head>
    <body>
        <h1>GeeksforGeeks</h1> 
        <h2>DOM console.group() Method</h2> 
        <p>
         To view the message in the console 
         press the F12 key on your keyboard.
        </p>
        <script>
            console.log("GeeksforGeeks offers the following courses:");
            console.group("Courses");
            console.log("1\. fork python");
            console.log("2\. fork cpp");
            console.log("3\. fork java");
            console.log("4\. Interview preparation");
        </script>
    </body>
</html>                    
```

**输出:**
![](img/0569530f27a7baf0a10c1305a9bbef7e.png)
**控制台视图:**
![](img/d8a15aaf3d203641bf54ee9b270ce561.png)

**支持的浏览器:**下面列出了 *console.group()* 方法支持的浏览器:

*   谷歌 Chrome
*   Internet Explorer 11.0
*   Firefox 4.0
*   歌剧
*   Safari 4.0