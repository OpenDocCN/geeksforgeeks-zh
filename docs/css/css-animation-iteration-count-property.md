# CSS |动画-迭代-计数属性

> 原文:[https://www . geesforgeks . org/CSS-动画-迭代-计数-属性/](https://www.geeksforgeeks.org/css-animation-iteration-count-property/)

CSS 中的**动画-迭代-计数属性**用于指定动画重复的次数。它可以指定为无限来无限重复动画。

**语法:**

```html
animation-iteration-count: number|infinite|initial|inherit;
```

**属性值:**

*   **数字:**该属性值用于定义动画应该播放的次数。默认值为 1。
*   **无限:**该属性值指定动画应播放无限次(永远)。
*   **初始值:**该属性值用于将该属性设置为默认值。
*   **inherit:** 该值用于从其父元素继承该属性。

**示例:** HTML 程序说明动画-迭代-计数

```html
<!DOCTYPE html> 
<html> 
    <head> 
        <title>
            CSS | animation-iteration-count Property
        </title>
        <style> 
            .geeks { 
                font-size: 40px; 
                text-align:center; 
                font-weight:bold; 
                color:#090; 
                padding-bottom:5px; 
                font-family:Times New Roman; 
            } 

            .geeks1 { 
                font-size:17px; 
                font-weight:bold; 
                text-align:center; 
                font-family:Times New Roman; 
            } 

            #one { 
                animation-name: example; 
                animation-duration: 2s; 

                /* Animation will be repeated twice */
                animation-iteration-count: 2; 
            } 

            #two { 
                animation-name: example; 
                animation-duration: 2s; 

                /* Animation will be repeated infinitely */
                animation-iteration-count: infinite; 
            } 
            @keyframes example { 
                from { 
                    background-color: orange; 
                } 
                to { 
                    background-color: white; 
                } 
            } 
        </style> 
    </head> 
    <body> 
        <div class = "geeks">
            GeeksforGeeks
        </div> 

        <div class = "geeks1">
            A computer science portal for geeks
        </div>

        <!-- Animation of the text inside the h2 tag  
             below will be repeated twice only -->
        <h2 id="one">
            This text changes its color two times.
        </h2> 

        <!-- Animation of the text inside the h2 tag 
             below will be repeated infinitely -->
        <h2 id="two">
            This text changes its color infinite times.
        </h2> 
    </body> 
</html>                                                       
```

**支持的浏览器:***动画-迭代-计数属性*支持的浏览器如下:

*   谷歌 Chrome 43.0
*   Internet Explorer 10.0
*   Firefox 16.0
*   Opera 30.0
*   Safari 9.0