# 如何在 CSS 中使用 flex 来缩小图像？

> 原文:[https://www . geeksforgeeks . org/如何使用-flex-to-缩图-in-css/](https://www.geeksforgeeks.org/how-to-use-flex-to-shrink-an-image-in-css/)

您可以通过使用 CSS 中的[折绕](https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=&cad=rja&uact=8&ved=2ahUKEwixz9n1m_nxAhVDmuYKHRXpC2IQFjACegQICBAD&url=https%3A%2F%2Fwww.geeksforgeeks.org%2Fcss-flex-wrap-property%2F&usg=AOvVaw1LhEjolyWe82D41GFOeaVN)属性来轻松地缩小图像，它指定折绕项目是强制成单行还是折绕成多行。*折绕*属性允许控制线条堆叠的方向。它用于指定单行或多行格式，以在 flex 容器内伸缩项目。

**语法:**

```html
flex-wrap: wrap
```

**注意:** *包裹* 用于将伸缩项分割成多行。它使弹性项根据弹性项宽度换行到多行。

**示例:**为了缩小图像，必须使图像的宽度达到 100%，这样图像就占据了 100%的大小< div > **。**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <style>
        .container {
            display: -webkit-flex;
            -webkit-flex-wrap: wrap;
            display: flex;
            flex-wrap: wrap;
            background-color: grey;
        }

        img {
            width: 100%;
        }

        div {
            flex: 1;
            padding: 10px;
            margin: 10px;
        }
    </style>
</head>

<body>
    <div class="container">
        <div class="image">
            <img src=
"https://media.geeksforgeeks.org/wp-content/cdn-uploads/20190710102234/download3.png" />
        </div>
        <div class="image">
            <img src=
"https://media.geeksforgeeks.org/wp-content/cdn-uploads/20190710102234/download3.png" />
        </div>
        <div class="image">
            <img src=
"https://media.geeksforgeeks.org/wp-content/cdn-uploads/20190710102234/download3.png" />
        </div>
    </div>
</body>

</html>
```

**输出:**

![](img/964be9b3917353be6ea87e1e8aa68ebd.png)

伸缩包装属性