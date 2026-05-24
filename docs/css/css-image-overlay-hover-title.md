# CSS 图像叠加悬停标题

> 原文:[https://www . geesforgeks . org/CSS-image-overlay-hover-title/](https://www.geeksforgeeks.org/css-image-overlay-hover-title/)

在本文中，我们将学习如何使用 HTML 和 CSS，在鼠标悬停在图像上时创建一个图像覆盖标题。这可以通过在单个 div(容器)中包含图像和标题 div 来实现。标题 div 最初是不可见的。只有当鼠标悬停在图像上时，它才变得可见。

标题 div 相对于容器 div(父级)定位。通过设置**“不透明度:0”**或**“z-索引:-1”**(z-索引:-1 表示标题 div 层现在位于容器 div 的后面，因此不可见)。如下例所示，通过分别设置****“不透明度:1”**或**“z-index:0”**，仅在悬停时可见。**

****示例 1:** 这里，标题 div 的不透明度最初为 0，悬停时变为 1，过渡时间为 0.6 秒。**

```html
<!DOCTYPE html>
<html>

<head>
    <style>
        .container {
            position: relative;
            width: 30%;
        }

        #gfg-img {
            width: 100%;
            display: block;
        }

        .title {
            background-color: rgb(0, 0, 0, 0.5);
        /*positioned relative to parent div (container) */
            position: absolute;    
/* bottom margin is 0 so that it 
     coincides with container's bottom margin*/
            bottom: 0;             
            color: white;
            width: 100%;
            font-size: 25px;
            padding: 15px 0;
            text-align: center;
            /*invisible because opacity is 0*/
            opacity: 0;            
            transition: 0.6s;
        }

        .container:hover .title {
        /*becomes visible on hover*/ 
            opacity: 1;          
        }
    </style>
</head>

<body>
    <h1>Hover over image to see title</h1>
    <div class="container">
        <img id="gfg-img" src="gfg.png">
         <!--overlay title-->
        <div class="title">GeeksforGeeks</div> 
    </div>
</body>

</html>
```

****输出:****

**<video class="wp-video-shortcode" id="video-450086-1" width="640" height="360" loop="1" autoplay="" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200706001212/title1.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200706001212/title1.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200706001212/title1.mp4)</video>**

****示例 2:** 这里，title div 的 z-index 最初是-1，这意味着它位于容器 div 的后面。悬停时变为 0，过渡时间为 0.8 秒，如下所示:**

```html
<!DOCTYPE html>
<html>

<head>
    <style>
        .container {
            position: relative;
            width: 50%;
        }

        #gfg-img {
            width: 100%;
            display: block;
        }

        .title {
            background-color: rgb(255, 255, 255, 0.4);
            position: absolute;
/*title is positioned at the top of container div*/ 
            top: 0; 
            color: white;
            width: 100%;
            font-size: 25px;
            padding: 15px 0;
            text-align: center;
 /*title div is at the back of container and hence not visible*/
            z-index: -1;
            transition: 0.8s;
        }

        .container:hover .title {
/*becomes visible on hover as title comes on top of container*/
            z-index: 0; 
        }
    </style>
</head>

<body>
    <h1>Hover over image to see title</h1>
    <div class="container">
        <img id="gfg-img" src="gfg2.jpg">
         <!--overlay title-->
        <div class="title">GeeksforGeeks</div>
    </div>
</body>

</html>
```

****输出:**** 

**<video class="wp-video-shortcode" id="video-450086-2" width="640" height="360" loop="1" autoplay="" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200706001740/title2.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20200706001740/title2.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200706001740/title2.mp4)</video>**