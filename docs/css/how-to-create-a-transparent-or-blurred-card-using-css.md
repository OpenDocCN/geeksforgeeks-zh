# 如何使用 CSS 创建透明或模糊的卡片？

> 原文:[https://www . geeksforgeeks . org/如何使用 css 创建透明或模糊卡片/](https://www.geeksforgeeks.org/how-to-create-a-transparent-or-blurred-card-using-css/)

在本文中，我们将使用基本的 [HTML](https://www.geeksforgeeks.org/html-tutorials/) 和 [CSS](https://www.geeksforgeeks.org/css-tutorials/) 属性创建一个透明或模糊的卡片。模糊效果也称为玻璃效果。

**进场:**

*   Mark on [to create the layout of the card.](https://www.geeksforgeeks.org/html-body-tag/)
*   Define the class of each component to use CSS properties.
*   To apply a glass or blur effect, use the [background filter](https://www.geeksforgeeks.org/css-backdrop-filter-property/) property to blur the card.

**示例:**使用上述方法创建玻璃或模糊或透明卡片。如第一步所述，我们将在 body 标签下创建卡片的布局。

## HTML

```html
<!DOCTYPE html>
<html>

<head>
    <title>Page Title</title>
</head>

<body>
    <div class="background">
        <div class="card">
            <img src=
"https://media.geeksforgeeks.org/wp-content/cdn-uploads/20190710102234/download3.png"
                alt="image" />
            <h1>GeeksforGeeks</h1>
            <h3>Happy Coding</h3>
        </div>
    </div>
</body>

</html>
```