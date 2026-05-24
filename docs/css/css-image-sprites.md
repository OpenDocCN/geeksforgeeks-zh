# CSS |图像喷溅

> 哎哎哎:# t0]https://www . geeksforgeeks . org/CSS-image-sprite/

它基本上是一个图像，是不同图像的集合，放在一起形成一个图像。使用图像精灵有两个主要原因:

*   因为只使用单个图像，所以页面加载更快。
*   它减少了用于加载多个图像的带宽。这样，消耗数据更少。

图像精灵通常用于设计图形社交媒体栏或导航栏，以使其同时更具吸引力和效率。这只是在 HTML 和 CSS 中实现更有效的放置图像和设计网页的方法。

**使用图像:**
![icon image](img/dd2cf5bca6d0b17ad5e66e5bba9a2458.png)

**示例:**

```html
<!DOCTYPE html>
<html>
    <head>
        <style>
            #navlist {
                position: relative;
            }            
            #navlist li {
                margin: 0;
                padding: 0;
                list-style: none;
                position: absolute;
                top: 0;
            }            
            #navlist li, #navlist a {
                height: 100px;
                display: block;
            }           
            .gfg {
                width: 100px;
                left:0px;
                background: url(
'https://media.geeksforgeeks.org/wp-content/uploads/icon.png') -0px -0px;
            }
            .gfg1 {
                width: 100px; 
                left:120px;
                background: url(
'https://media.geeksforgeeks.org/wp-content/uploads/icon.png') -0px -140px;
            }
            .gfg2 {
                width: 100px; 
                left:240px;
                background: url(
'https://media.geeksforgeeks.org/wp-content/uploads/icon.png') -300px -140px;
            } 
        </style>
    </head>
    <body>
        <ul id="navlist">
            <li class = "gfg"><a href="#"></a></li>
            <li class = "gfg1"><a href="#"></a></li>
            <li class = "gfg2"><a href="#"></a></li>
        </ul>
    </body>
</html>                                    
```

**输出:**
![sprite image](img/e2876c9eeebeac4954afb7ad755599e0.png)