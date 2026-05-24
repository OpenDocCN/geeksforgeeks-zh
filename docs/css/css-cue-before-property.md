# CSS 提示-属性前

> 原文:[https://www.geeksforgeeks.org/css-cue-before-property/](https://www.geeksforgeeks.org/css-cue-before-property/)

**CSS 提示前属性**用于定义在元素之前播放的听觉图标，以区分和设置元素。

**语法:**

```html
cue-before: url|none;
```

**参数:**该属性接受两个值，如上所述，如下所述:

*   **url:** 此参数保存听觉图标资源。如果用户不能呈现所提到的听觉图标，那么它将产生替代提示，例如铃声。
*   **无:**此参数定义不使用听觉图标。

**例 1:**

## 超文本标记语言

```html
<!DOCTYPE html> 
<html> 

<head> 
    <style> 
        .gfg { 
            cue-before: none; 
        } 
    </style> 
</head> 

<body style="text-align: center;"> 
    <h1 style="color: green;">GeeksforGeeks</h1> 
    <p class="gfg">CSS cue-before Property</p>

    <audio controls> 
        <source src= 
"https://media.geeksforgeeks.org/wp-content/uploads/20190625153922/frog.mp3"
        type="audio/mp3"> 
    </audio> 
</body> 

</html> 
```

**输出:**

![](img/f01335964d07a8b618cc17b2ca2c1204.png)

**例 2:**

## 超文本标记语言

```html
<!DOCTYPE html> 
<html> 

<head> 
    <style> 
        .gfg { 
            cue-before: url("bell.wav");  
        } 
    </style> 
</head> 

<body style="text-align: center;"> 
    <h1 style="color: green;">GeeksforGeeks</h1> 
    <p class="gfg">CSS cue-before Property</p>

    <audio controls> 
        <source src= 
"https://media.geeksforgeeks.org/wp-content/uploads/20190625153922/frog.mp3"
        type="audio/mp3"> 
    </audio> 
</body> 

</html> 
```

**输出**

![](img/f01335964d07a8b618cc17b2ca2c1204.png)

**支持的浏览器:**这个属性在 CSS3 中不推荐使用，所以这个属性不支持主要的浏览器。