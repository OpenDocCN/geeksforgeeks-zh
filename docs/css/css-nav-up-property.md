# CSS |导航属性

> 原文:[https://www.geeksforgeeks.org/css-nav-up-property/](https://www.geeksforgeeks.org/css-nav-up-property/)

CSS **向上导航**属性用于从键盘导航导航键。此属性定义用户使用导航键导航时的焦点位置。**向上导航**可以与**向右导航**、**向下导航**和**向左导航**属性一起使用。

**语法:**

```html
 nav-up: auto | id | target-name | initial | inherit;
```

**属性:**

*   **auto:** 默认情况下，浏览器定义导航哪个元素。
*   **< id > :** 它定义了要导航的 id。
*   **<目标-名称> :** 定义要导航的目标。
*   **初始值:**为默认值。
*   **继承:**从其父元素继承。

**注意:**这个属性只支持 Opera 12.0。
下面举例说明属性:

**例:1**

```html
<!DOCTYPE html> 
<html> 

<head> 
    <title>CSS nav-up Property</title> 
    <link rel="stylesheet" href= 
"https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css"> 
    <style> 
        button { 
            position: absolute; 
        } 

        h1 { 
            color: green; 
        } 

        button { 
            background-color: #80ff80; 
            nav-right: auto; 
            nav-left: auto; 
            nav-down: auto; 
            nav-up: auto; 
            border-radius: 25px; 
            font-size: 20px; 
        } 

        #Geeks1 { 
            top: 35%; 
            left: 43%; 
            nav-index: 1; 
        } 

        #Geeks2 { 
            top: 50%; 
            left: 65%; 
            nav-index: 2; 
        } 

        #Geeks3 { 
            top: 65%; 
            left: 43%; 
            nav-index: 3; 
        } 

        #Geeks4 { 
            top: 50%; 
            left: 20%; 
            nav-index: 4; 
        } 
    </style> 
</head> 

<body> 
    <center> 
        <h1>GeeksforGeeks</h1> 
        <h4>CSS nav-up Property</h4> 
        <p> 
            Press the <samp>Shift</samp> 
        key while navigating with the arrow keys. 
        </p> 
    </center> 
    <button id="Geeks1">Button 
    <i class="fa fa-arrow-circle-up"></i> 
    </button> 
    <button id="Geeks2">Button 
    <i class="fa fa-arrow-circle-right"></i> 
    </button> 
    <button id="Geeks3">Button 
    <i class="fa fa-arrow-circle-down"></i> 
    </button> 
    <button id="Geeks4"> 
    <i class="fa fa-arrow-circle-left"></i> 
    Button 
    </button> 

    <div> 

    </div> 
</body> 

</html> 
```

**输出:**
![](img/fe4d4b89d945f61de908a8eedda4c45a.png)

**支持的浏览器:**主要浏览器不支持 **CSS 导航属性**

**浏览器特定扩展:**CSS 导航工具有浏览器特定扩展。

*   谷歌 Chrome *-webkit-*
*   Internet Explorer *-ms-*
*   Firefox *-moz-*
*   Safari *-webkit-*
*   Opera *-webkit-*