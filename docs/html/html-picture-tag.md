# HTML picture 标签

> 原文:[https://www.geeksforgeeks.org/html-picture-tag/](https://www.geeksforgeeks.org/html-picture-tag/)

HTML 中的 **<图片>标签**用于为网络开发者提供指定图像资源的灵活性。<图片>标签包含 [<来源>](https://www.geeksforgeeks.org/html-source-tag/) 和 [< img >](https://www.geeksforgeeks.org/html-img-tag/) 标签。属性值被设置为加载更合适的图像。
img>元素用于图片声明块的最后一个子元素。< img >元素用于为不支持该元素的浏览器提供向后兼容性，或者如果没有匹配的源标签。

<picture>标签类似于<video>和

<audio>。我们添加不同的源，第一个符合偏好的源是将要使用的源。</audio></video></picture> 

**语法:**

```html
<picture>
    Image and source tag
<picture>
```

下面的例子说明了 HTML 中的<picture>标签:</picture>

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <style>
        body {
            text-align: center;
        }

        h1 {
            color: green;
        }
    </style>
</head>

<body>
    <h1>GeeksforGeeks</h1>

    <h2>HTML <picture> Tag</h2>

    <picture>
        <source media="(min-width: 700px)" 
                srcset=
"https://media.geeksforgeeks.org/wp-content/uploads/20190825000042/geeks-221.png">

        <source media="(min-width: 450px)" 
                srcset=
"https://media.geeksforgeeks.org/wp-content/uploads/20190802021607/geeks14.png">

        <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20190808102629/geeks15.png" 
             alt="GFG" style="width:auto;">
    </picture>
</body>

</html>
```

**输出:**

![](img/cd37dbc9e8007189d6b8de8e875dc272.png)

**支持的浏览器:**

*   谷歌 Chrome 38.0
*   Internet Explorer 13.0
*   Firefox 38.0
*   Safari 9.1
*   Opera 25.0