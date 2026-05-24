# CSS |图片库

> 原文:[https://www.geeksforgeeks.org/css-image-gallery/](https://www.geeksforgeeks.org/css-image-gallery/)

图像库用于存储和显示图片集。这个例子使用 HTML 和 CSS 创建了一个响应的图像库。

**步骤 1:** 创建一个基本的画廊结构

*   每个图库包含多个分区。
*   每个 div 部分包含一个图像及其描述。

```html
<div class="gallery">
  <div class="box"> 
    <div class="image"> Image Added Here </div>
    <div class="text"> Text Added Here  </div>
  </div>

```

**步骤 2:** 使用 CSS 设置文件的样式

*   **设计画廊容器:**

    ```html
    .gallery {
      width:100%;
      display:flex;
      flex-flow: row wrap;
    }

    ```

    *   将显示属性设置为 flex。这意味着图库容器中的元素将具有 flex 上下文。
    *   将 flex-flow 属性设置为行换行。它设置伸缩方向和伸缩环绕样式。
*   **盒子造型:**

    ```html
    .box {
        flex-basis: 20%;
        width: 100%;
        padding: 10px;
        margin: 8px;

        // Set the blur shadow
        box-shadow: 1px 1px 15px 1px green; 
    }

    ```

**步骤 3:** 使用@media 查询创建响应性的图库。

```html
@media only screen and (max-width: 300px) { 
.box {
    flex-basis: 100%;
}

```

**示例:**

```html
<!DOCTYPE html>
<html>

<head>
    <style>

        /* style to set body of page */
        body {
            width:100%; 
            margin:auto;
        }
        .gallery {
            width:100%;
            display:flex;
            flex-flow: row wrap;
        }
        .box {
            flex-basis:20%;
            width:100%;
            padding:10px;
            margin:8px;
            box-shadow: 1px 1px 1px 1px green;
        }
        .text {
            text-align:center;
            margin-top:5px;
        }
        .image:hover {
            border: 3px solid green;
        }

        /* media query used here */
        @media only screen and (max-width: 300px) { 
            .box {
                flex-basis: 100%;
            }
        }

        @media only screen and (max-width:500px) {
            .box {
                flex-basis: 40%;
            }
        }
    </style>
</head>

<body>
    <div class = "gallery">
        <div class = "box">
            <div class = "image">
                <a target="_blank" href=
"https://media.geeksforgeeks.org/wp-content/uploads/geeksforgeek.png">
                    <img src =
"https://media.geeksforgeeks.org/wp-content/uploads/geeksforgeek.png" 
                width = "300" height = "300">
                </a>
            </div>

            <div class = "text">
                Geeks Classes Image
            </div>
        </div>

        <div class = "box">
            <div class = "image">
                <a target="_blank" href=
"https://media.geeksforgeeks.org/wp-content/uploads/geeksforgeeks-22.png">
                    <img src =
"https://media.geeksforgeeks.org/wp-content/uploads/geeksforgeeks-22.png"
                width = "300" height = "300">
                </a>
            </div>

            <div class = "text">
                GeekforGeeks Image
            </div>
        </div>

        <div class = "box">
            <div class = "image">
                <a target="_blank" href=
"https://media.geeksforgeeks.org/wp-content/uploads/geeksforgeeks-10.png">
                    <img src = 
"https://media.geeksforgeeks.org/wp-content/uploads/geeksforgeeks-10.png" 
                width = "300" height = "300">
                </a>
            </div>

            <div class = "text">
                Geeks Image
            </div>
        </div>
</body>

</html>                                    
```

**输出:**
![image gallery](img/294385a19ae8b83128f711920d113955.png)