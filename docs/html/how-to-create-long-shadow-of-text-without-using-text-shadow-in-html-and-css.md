# 如何在 HTML 和 CSS 中不使用文本阴影的情况下创建文本的长阴影？

> 原文:[https://www . geesforgeks . org/如何在不使用 html 和 css 中的文本阴影的情况下创建长文本阴影/](https://www.geeksforgeeks.org/how-to-create-long-shadow-of-text-without-using-text-shadow-in-html-and-css/)

阴影确实是给任何文本赋予深度和三维外观的好方法。一般来说，我们使用文本阴影来给文本阴影，但是这个阴影很短，为了创建长阴影*(其中文本像反射一样可见的阴影)*我们必须在选择器和倾斜功能之前使用。

**方法:**方法是先使用倾斜创建倾斜文本，然后在之前使用*来制作使用倾斜功能创建阴影的原始文本。*

**HTML 代码:**在本节中，我们将文本包装在 *h1* 标签中。

## HTML

```html
<!DOCTYPE html>
<html>

<head>
    <title>Long Shadow Effect</title>
</head>

<body>
    <div class="center">
        <h1 data-title="GEEKS">GEEKS</h1>
    </div>
</body>

</html>
```