# html 5 中页面加载时如何预加载视频？

> 原文:[https://www . geesforgeks . org/如何在网页加载 html5 时预加载视频/](https://www.geeksforgeeks.org/how-to-preload-the-video-when-the-page-loads-in-html5/)

HTML [**<预加载>**](https://www.geeksforgeeks.org/html-video-preload-attribute/) 属性用于指定页面加载时开发者认为应该加载视频的方式。

**语法**

```html
<video preload=""> </video>
```

*预加载*属性自动、元数据和无有 3 个值。

**注意:**空字符串导致默认**自动**属性值。

**示例 1:** 以下示例使用*预加载*属性的 *none* 属性值来演示*视频*元素。

## 超文本标记语言

```html
<!DOCTYPE html> 
<html> 
 <body> 
    <center> 
        <h1 style="color:green;">GeeksforGeeks</h1> 

        <h3>HTML preload Attribute</h3> 

        <video width="400" height="200" controls preload="none"> 
            <source src= 
"https://media.geeksforgeeks.org/wp-content/uploads/20190616234019/Canvas.move_.mp4"
                    type="video/mp4"> 
            <source src= 
"https://media.geeksforgeeks.org/wp-content/uploads/20190616234019/Canvas.move_.ogg"
                    type="video/ogg"> 
        </video> 
    </center> 
</body> 

</html> 
```

**输出:**

![](img/cdd5ed7e534e5746dad857bb95d97efe.png)

无值预加载

**示例 2:** 以下示例使用*自动*属性值演示了*视频*元素。

## 超文本标记语言

```html
<!DOCTYPE html> 
<html> 
<body> 
    <center> 
        <h1 style="color:green;">GeeksforGeeks</h1> 

        <h3>HTML preload Attribute</h3> 

        <video width="400" height="200" controls preload="auto"> 
            <source src= 
"https://media.geeksforgeeks.org/wp-content/uploads/20190616234019/Canvas.move_.mp4"
                    type="video/mp4"> 
            <source src= 
"https://media.geeksforgeeks.org/wp-content/uploads/20190616234019/Canvas.move_.ogg"
                    type="video/ogg"> 
        </video> 
    </center> 
</body> 

</html> 
```

**输出:**

![](img/b869519bbf63e024633c64fb6dd4986c.png)

用自动值预加载