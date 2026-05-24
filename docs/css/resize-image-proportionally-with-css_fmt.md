# 使用 CSS 按比例调整图像大小

> 原文：[https://www.geeksforgeeks.org/resize-image-proportionally-with-css/](https://www.geeksforgeeks.org/resize-image-proportionally-with-css/)

responsive web 中使用了 responsive image 属性，该属性会自动调整图像大小以适应 div 容器。CSS 中的 `max-width` 属性用于创建调整图像大小属性。如果在 HTML 中定义了图像的 `width` 和 `height`，则 `resize` 属性将不起作用。

## 语法

```html
img {
    max-width:100%;
    height:auto;
}
```

如果需要，也可以使用 `width` 代替 `max-width`。关键是使用 `height:auto` 覆盖图像上已经存在的任何 `height="…"` 属性。
CSS 属性 `max-width` 和 `max-height` 很好用，但是很多浏览器不支持。

## 例 1

```html
<!DOCTYPE html>
<html> 
    <head> 
        <title>cell padding</title> 
        <style> 
            .gfg {
                width:auto;
                text-align:center;
                padding:20px;
            }
            img {
                max-width:100%;
                height:auto;
            }
        </style> 
    </head> 
    <body> 
        <div class = "gfg">
            <p id="my-image"><img src=
"https://media.geeksforgeeks.org/wp-content/uploads/geeksforgeeks-17.png">
            </p>
        </div>
    </body> 
</html>
```

## 输出

![](img/889495b4c1bdfcefa695c841ee7cf27a.png)

常见的用法是设置 `max-width:100%; height:auto;`，所以大图像不会超过它们的容器宽度。另一种方法是使用 `object-fit` 属性，这将适合图像，而不改变比例。

## 例 2

```html
<!DOCTYPE html>
<html> 
    <head> 
        <title>cell padding</title> 
        <style> 
            .gfg {
                width:auto;
                text-align:center;
                padding:20px;
            }
            img {
                width: 100%;
                height: 100%;
                object-fit: contain;
            }
        </style> 
    </head> 
    <body> 
        <div class = "gfg">
                <p id="my-image"><img src=
"https://media.geeksforgeeks.org/wp-content/uploads/geeksforgeeks-17.png">
            </p>
        </div>
    </body> 
</html>
```

## 输出

![](img/889495b4c1bdfcefa695c841ee7cf27a.png)

HTML 是网页的基础，通过构建网站和网络应用程序用于网页开发。您可以通过以下 [HTML 教程](https://www.geeksforgeeks.org/html-tutorials/)和 [HTML 示例](https://www.geeksforgeeks.org/html-examples/)从头开始学习 HTML。

CSS 是网页的基础，通过设计网站和网络应用程序用于网页开发。你可以通过以下 [CSS 教程](https://www.geeksforgeeks.org/css-tutorials/)和 [CSS 示例](https://www.geeksforgeeks.org/css-examples/)从头开始学习 CSS。