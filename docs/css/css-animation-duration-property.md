# CSS |动画时长属性

> 原文:[https://www . geesforgeks . org/CSS-动画-时长-属性/](https://www.geeksforgeeks.org/css-animation-duration-property/)

CSS 中的**动画持续时间**属性用于定义动画完成一个周期需要多长时间。也就是说，它用于指定动画播放的持续时间。

**语法:**

```html
animation-duration: time|initial|inherit;
```

**属性值:**

*   **时间:**该值用于指定动画完成一个周期的时间长度。这可以用秒或毫秒来指定。默认值为 0，这意味着不会出现动画。
*   **初始值:**该值用于将属性设置为默认值。
*   **inherit:** 该值用于从其父元素继承属性。

**示例:** HTML 程序，说明 CSS 中的动画时长属性。

```html
<!DOCTYPR html>
<html>

<head>
    <title>
        CSS | animation-duration Property
    </title>
    <style>
        #gfg1 {
            animation-name: text;
            animation-duration: 5s;
            animation-iteration-count: infinite;
        }

        #geek1 {
            font-size: 40px;
            text-align: center;
            font-weight: bold;
            color: #090;
            padding-bottom: 5px;
        }

        #geek2 {
            font-size: 17px;
            font-weight: bold;
            text-align: center;
        }

        @keyframes text {
            from {
                margin-top: 400px;
            }
            to {
                margin-top: 0px;
            }
        }
    </style>
</head>

<body>
    <!-- The below div is animated for a duration of 5s 
       and will be played an infinite number of times -->
    <div id="gfg1">
        <div id="geek1">
            GeeksforGeeks
        </div>
        <div id="geek2">
            A computer science portal for geeks
        </div>
    </div>
</body>

</html>                                    
```

**输出:**
![](img/8a6413d7ed7a70ff3fabb780bde8277c.png)

**支持的浏览器:***动画时长属性*支持的浏览器如下:

*   谷歌 Chrome 43.0
*   Internet Explorer 10.0
*   Firefox 16.0
*   Opera 30.0
*   Safari 9.0