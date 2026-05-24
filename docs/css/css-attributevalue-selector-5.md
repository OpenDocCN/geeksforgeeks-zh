# CSS |【属性~ =值】选择器

> 原文:[https://www . geesforgeks . org/CSS-attribute value-selector-5/](https://www.geeksforgeeks.org/css-attributevalue-selector-5/)

[attribute~="value"]选择器用于选择那些属性值包含指定单词的元素。“值”必须作为一个单独的词出现在属性中，而不是作为另一个词的一部分，即如果指定了[title~=Geeks]，则所有带有 Geeks 标题的元素都会被选中。

**语法:**

```html
[attribute~=value] {
    // CSS property
}

```

**例 1:**

```html
<!DOCTYPE html> 
<html> 
    <head> 
        <style> 
            [class~="Geeks"] { 
                background: green; 
                color: white; 
            } 
        </style> 
    </head> 

    <body style = "text-align:center;"> 

        <div class="Geeks Class">
            First div Element
        </div> 

        <div class="GeeksforGeeks">
            Second div Element
        </div> 

        <div class="My Geeks">
            Third div Element
        </div> 

        <div class="MyGeeks">
            Fourth div Element
        </div> 
    </body> 
</html>                                 
```

**输出:**
![](img/b17b0ba48d9280ad75591ebd45296fe2.png)

**例 2:**

```html
<!DOCTYPE html> 
<html> 
    <head> 
        <title> 
            CSS [attribute~=value] Selector 
        </title> 

        <style> 
            [class~=Geeks] { 
                border: 5px solid blue; 
            } 
        </style> 
    </head> 

    <body> 
        <h2 style = "text-align:center">[attribute~=value] Selector</h2> 

        <img src= 
"https://media.geeksforgeeks.org/wp-content/uploads/geeksforgeeks-logo.png"
        class="Geeks Class" alt="gfg"> 

        <img src= 
"https://media.geeksforgeeks.org/wp-content/uploads/geeks-25.png"
        class="Geeks" alt="geeks"> 

        <img src= 
"https://media.geeksforgeeks.org/wp-content/uploads/geeksforgeeks-10.png"
        class="GeeksforGeeks" alt="gfg"> 
    </body> 
</html>                     
```

**输出:**
![](img/2113e0812f7eb7bc273689a5d7c5eef8.png)

**支持的浏览器:**T2【属性~ =值】选择器支持的浏览器如下:

*   谷歌 Chrome 4.0
*   Internet Explorer 7.0
*   Firefox 2.0
*   Safari 3.1
*   歌剧 9.6