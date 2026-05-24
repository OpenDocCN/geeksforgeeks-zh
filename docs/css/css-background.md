# CSS 背景

> 原文:[https://www.geeksforgeeks.org/css-background/](https://www.geeksforgeeks.org/css-background/)

CSS 背景属性用于定义元素的背景效果。设计背景有很多属性。
CSS 背景属性如下:

*   [CSS 背景色属性](https://www.geeksforgeeks.org/css-background-color-property/#:~:text=The%20background%2Dcolor%20property%20in,to%20read%20for%20the%20user.):CSS 中的背景色属性用于指定元素的背景色。
*   [CSS 背景图像属性](https://www.geeksforgeeks.org/css-background-image-property/):背景图像属性用于为一个元素设置一个或多个背景图像。
*   [CSS 背景-重复属性](https://www.geeksforgeeks.org/css-background-repeat-property/#:~:text=The%20background%2Drepeat%20property%20in,will%20be%20repeated%20or%20not.&text=The%20last%20image%20will%20be,fit%20in%20the%20browser%20window.):CSS 中的背景-重复属性用于水平和垂直重复背景图像。
*   [CSS 背景-附件属性](https://www.geeksforgeeks.org/css-background-attachment-property/#:~:text=The%20property%20background%2Dattachment%20property,applied%20to%20all%20HTML%20elements.):CSS 中的属性背景-附件属性用于指定背景图像相对于其容器的附件种类。
*   [CSS 背景-位置属性](https://www.geeksforgeeks.org/css-background-position-property/):在 CSS 中，主体-位置属性主要用于设置某个位置的图像。
*   [CSS 背景原点属性](https://www.geeksforgeeks.org/css-background-origin-property/):背景原点是 CSS 中定义的一个属性，有助于调整网页的背景图像。
*   [CSS 背景-剪辑属性](https://www.geeksforgeeks.org/css-background-clip-property/):CSS 中的背景-剪辑属性用于定义如何在元素内扩展背景(颜色或图像)。

[**背景色属性**](https://www.geeksforgeeks.org/css-background-color-property/#:~:text=The%20background%2Dcolor%20property%20in,to%20read%20for%20the%20user.) **:此属性指定元素的背景色。颜色名称也可以给出为:“绿色”，十六进制值为“#5570f0”，RGB 值为“rgb(25，255，2)”。
**语法:****

```html
body {
   background-color:color name
}
```

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <style>
        h1 {
            background-color: blue;
        }
    </style>
</head>

<body>
    <h1>Geeksforgeeks</h1>
</body>

</html>
```

**输出:**

![](img/3ae88409924e3cea46825aaa38e27ea2.png)

[**背景图像属性**](https://www.geeksforgeeks.org/css-background-image-property/) **:** 该属性指定用作元素背景的图像。默认情况下，图像是重复的，因此它覆盖了整个元素。
**语法:**

```html
body {
   background-image : link;
}
```

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>

    <style>
        body {
            background-image:
url("https://media.geeksforgeeks.org/wp-content/cdn-uploads/20190417124305/250.png");
        }
    </style>
</head>

<body>
    <h1>Geeksforgeeks</h1>
</body>

</html>
```

**输出:**

![](img/9159ade368cb674156fd4d1246b9ee6a.png)

[**背景重复属性**](https://www.geeksforgeeks.org/css-background-repeat-property/#:~:text=The%20background%2Drepeat%20property%20in,will%20be%20repeated%20or%20not.&text=The%20last%20image%20will%20be,fit%20in%20the%20browser%20window.) **:默认情况下，背景图像属性水平和垂直重复图像。
**语法:**水平重复图像**

```html
body {
   background-image:link;
   background-repeat: repeat:x;
}
```

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <style>
        body {
            background-image:
url("https://media.geeksforgeeks.org/wp-content/cdn-uploads/20190417124305/250.png");
            background-repeat: repeat-x;
        }
    </style>
</head>

<body>
    <h1>"Hello world"</h1>
</body>

</html>
```

**输出:**

![](img/8360877b0cfe154b737be270fda2f39d.png)

[**背景-附着属性**](https://www.geeksforgeeks.org/css-background-attachment-property/#:~:text=The%20property%20background%2Dattachment%20property,applied%20to%20all%20HTML%20elements.) **:该属性用于固定背景地面图像。图像不会随着页面滚动。
**语法:****

```html
body {
   background-attachment: fixed;
}
```

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <style>
        body {
            background-image:
url("https://media.geeksforgeeks.org/wp-content/cdn-uploads/20190417124305/250.png");
            background-attachment: fixed;
        }
    </style>
</head>

<body>
    <h1>Geeksforgeeks</h1>
</body>

</html>
```

**输出:**

![](img/71b45db81e09e7f05f40dd4e8c9e5474.png)

[**背景位置属性**](https://www.geeksforgeeks.org/css-background-position-property/) **:** 该属性用于将图像设置到特定位置。
**语法:**

```html
body {
   background-repeat:no repeat;
   background-position:left top;
}
```

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <style>
        body {
            background-image:
url("https://media.geeksforgeeks.org/wp-content/cdn-uploads/20190417124305/250.png");
            background-repeat: no-repeat;
            background-position: center;
        }
    </style>
</head>

<body>
    <h1>Geeksforgeeks</h1>
</body>

</html>
```

**输出:**

![](img/f08c0bc729fdedc0f9a24b92395a0691.png)