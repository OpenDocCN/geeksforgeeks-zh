# 如何在 bootstrap 中制作垂直可滚动行？

> 原文:[https://www . geesforgeks . org/如何制作垂直可滚动的引导行/](https://www.geeksforgeeks.org/how-to-make-vertical-scrollable-rows-in-bootstrap/)

这里的任务是在引导行中进行垂直滚动。

这可以通过以下方法实现:

**进场:**

*   使用**位置将下一行的所有 div 元素设为绝对；**属性(按列排列所有 div)。
*   使用**溢出-y: scroll 将滚动条添加到所有 div 元素；**属性。

**示例:**

```html
<!DOCTYPE html> 
<html lang="en"> 

<head> 
    <title>How to make vertical 
    scrollable in a bootstrap row?</title> 

    <meta charset="utf-8"> 
    <meta name="viewport"
        content="width=device-width, initial-scale=1"> 

    <link rel="stylesheet"
        href= 
"https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/css/bootstrap.min.css"> 
    <style>

       .vertical-scrollable> .row {
          position: absolute;
          top: 120px;
          bottom: 100px;
          left: 180px;
          width: 50%;
          overflow-y: scroll; 
        }
        .col-sm-8 { 
            color: white; 
            font-size: 24px; 
            padding-bottom: 20px; 
            padding-top: 18px; 
        } 

        .col-sm-8:nth-child(2n+1) { 
            background: green; 
        } 

        .col-sm-8:nth-child(2n+2) { 
            background: black; 
        } 

    </style> 
</head> 

<body> 
    <center> 
        <div class="container"> 

            <h1 style=
       "text-align:center;color:green;"> 
            GeeksforGeeks 
        </h1> 
            <h3> 
            To make vertical scrollable
            in a bootstrap row? 
        </h3> 
            <div class="container vertical-scrollable"> 
                <div class="row text-center"> 
                    <div class="col-sm-8">
                      1</div> 
                    <div class="col-sm-8">
                      2</div> 
                    <div class="col-sm-8">
                      3</div> 
                    <div class="col-sm-8">
                      4</div> 
                    <div class="col-sm-8">
                      5</div> 
                    <div class="col-sm-8">
                      6</div> 
                    <div class="col-sm-8">
                      7</div> 
                </div> 
            </div> 
        </div> 
    </center> 
</body> 

</html>
```

**输出:**

![](img/05fb9f34359249adcf61e0dad87420d8.png)