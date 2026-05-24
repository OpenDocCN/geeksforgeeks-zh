# 如何使用 CSS 给图像添加蒙版？

> 原文:[https://www . geeksforgeeks . org/如何使用 css 向图像添加遮罩/](https://www.geeksforgeeks.org/how-to-add-a-mask-to-an-image-using-css/)

CSS 中的**蒙版-图像**属性用于设置图像或文本的蒙版。它用于形成特定元素的掩膜层。您可以使用 CSS 中的[遮罩-图像属性](https://www.geeksforgeeks.org/css-mask-image-property/)为图像添加遮罩。在本文中，您将了解蒙版图像属性的不同属性值及其不同用途。

**语法:**

```html
mask-image: none | <make-source> | <image> | inherit | initial | unset
```

**属性值:**

*   **无:**未设置掩膜层，设置透明黑色层。
*   **< make-source >** :用于给出图片的来源 URL。
*   **<图像>** :使用线性渐变作为蒙版图像。
*   **继承:**继承父级的掩码属性。
*   **初始:**应用属性即匹配源的默认设置。
*   **取消设置:**放弃元素的当前掩码属性。

**例 1:** 使用 **<使-源>** 属性值。

**语法:**

```html
mask-image: url();
```

## 超文本标记语言

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8" />
    <title>Using make-source property value</title>

    <style>
      body {
        background-color: #fff;
      }
      .container {
        width: 335px;
        height: 334px;
        background-image: url(
"https://media.geeksforgeeks.org/wp-content/uploads/20210820105343/gfg.png");
        background-size: cover;
        background-position: center;
        background-repeat: no-repeat;
        -webkit-mask-box-image: url(STAR.svg);
        mask: url(STAR.svg);
      }
    </style>
  </head>

  <body>
    <div class="container"></div>
  </body>
</html>
```

**输出:**

![](img/ad09c315ea224989ac9f9661eaad068a.png)

**例 2:** 使用 **<形象>** 属性值。

**语法:**

```html
mask-image: linear-gradient();
```

**注意:**如果图像蒙版中有 100%的黑色，那么图像将完全可见，任何 100%透明的东西将完全隐藏，任何介于(0-100)之间的东西将部分蒙版图像。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8" />
    <title>Using image property</title>

    <style>
      body {
        background-color: #fff;
      }
      .container {
        width: 135px;
        height: 134px;
        background-image: url(
"https://media.geeksforgeeks.org/wp-content/uploads/20210820105343/gfg.png");
        background-size: cover;
        background-position: center;
        background-repeat: no-repeat;
        -webkit-mask-image: linear-gradient(
            to top, transparent 20%, black 80%);
        mask-image: linear-gradient(
            to top, transparent 20%, black 80%);
      }
    </style>
  </head>

  <body>
    <div class="container"></div>
  </body>
</html>
```

**输出:**

![](img/89de1fdc6a0e1800c921dd5755950277.png)