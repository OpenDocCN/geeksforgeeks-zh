# 如何使用 CSS 自动调整图像大小以适合 div 容器？

> 原文：[https://www.geeksforgeeks.org/how-to-auto-resize-an-image-to-fit-a-div-container-using-css/](https://www.geeksforgeeks.org/how-to-auto-resize-an-image-to-fit-a-div-container-using-css/)

若要自动调整图像或视频的大小以适合 `div` 容器，请使用 `object-fit` 属性。它用于指定图像或视频如何适合容器。

## 对象适配属性

该属性用于指定图像或视频如何调整容器的大小和适配容器。它告诉内容如何以各种方式适合特定的 `div` 容器，例如保持长宽比或者尽可能地扩大和占据空间。

### 示例 1

此示例描述了自动调整图像大小以适应 `div` 容器。此示例不包含 `object-fit` 属性。

```html
<!DOCTYPE html> 
<html> 
    <head> 
        <style>
            .geeks {
                width:60%;
                height:300px;
            }
            img {
                width:100%;
                height:100%;
            }
        </style>
    </head> 
    <body>
        <div class = "geeks">
            <img src="https://media.geeksforgeeks.org/wp-content/uploads/geeksforgeeks-25.png" 
        alt = "Geeks Image" />
        </div>
    </body> 
</html>
```

**输出：**
![](img/fc3859804a2085e57f14cdee84fad2b5.png)

在上例中由于没有使用 `object-fit` 属性，图像被挤压以适合容器，其原始纵横比被破坏。

### 示例 2

此示例用于在调整 `div` 容器大小时显示图像的一部分。

```html
<!DOCTYPE html> 
<html> 
    <head> 
        <style>
            .geeks {
                width:60%;
                height:300px;
            }
            img {
                width:100%;
                height:100%;
                object-fit:cover;
            }
        </style>
    </head> 
    <body>
        <div class = "geeks">
            <img src="https://media.geeksforgeeks.org/wp-content/uploads/geeksforgeeks-25.png" 
            alt = "Geeks Image" />
        </div>
    </body> 
</html>
```

**输出：**
![](img/fb450765958d804aca064e47ef76308e.png)

**注：** 使用 `object-fit: cover;` 将图像的边切掉，保留长宽比，同时也填充空间。

### 示例 3

此示例显示了一个未使用 `object-fit` 属性的图像。在此示例中，图像的大小是手动设置的，图像将无法保持其纵横比，也无法在调整浏览器窗口大小时根据 `div` 容器进行调整或调整大小。

```html
<!DOCTYPE html> 
<html> 
<head> 
    <style>
        body {
            text-align:center;
        } 
        img {
            width:400px;
            height:200px;
        }
    </style> 
</head> 
<body>
    <img src="https://media.geeksforgeeks.org/wp-content/uploads/geeksforgeeks-25.png" 
    alt="Geeks Image">
</body> 
</html>
```

**输出：**
![](img/cce5b3f86f5d5bd8b49f3d93bdf27be9.png)

### 示例 4

此示例显示了使用 `object-fit` 属性时图像的一部分或图像。在此示例中，图像的大小是手动设置的，并且也使用了 `object-fit` 属性。在这种情况下，调整浏览器大小时，图像将保持其纵横比，并且不会根据 `div` 容器调整大小。

```html
<!DOCTYPE html> 
<html> 
    <head> 
        <style>
            body {
                text-align:center;
            } 
            img {
                width:400px;
                height:200px;
                object-fit: cover;
            }
        </style> 
    </head> 
    <body>
        <img src="https://media.geeksforgeeks.org/wp-content/uploads/geeksforgeeks-25.png"
        alt="Geeks Image">
    </body> 
</html>
```

**输出：**
![](img/b772115e46b8344bbdf7ce5e138ead99.png)

**注：** 属性 `object-fit: cover;` 将切割图像的侧面，保留纵横比，同时填充空间。

## 相关资源

HTML 是网页的基础，通过构建网站和网络应用程序用于网页开发。您可以通过以下 [HTML 教程](https://www.geeksforgeeks.org/html-tutorials/)和 [HTML 示例](https://www.geeksforgeeks.org/html-examples/)从头开始学习 HTML。

CSS 是网页的基础，通过设计网站和网络应用程序用于网页开发。你可以通过以下 [CSS 教程](https://www.geeksforgeeks.org/css-tutorials/)和 [CSS 示例](https://www.geeksforgeeks.org/css-examples/)从头开始学习 CSS。