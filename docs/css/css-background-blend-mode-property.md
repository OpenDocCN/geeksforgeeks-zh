# CSS |背景-混合-模式属性

> 原文:[https://www . geesforgeks . org/CSS-background-blend-mode-property/](https://www.geeksforgeeks.org/css-background-blend-mode-property/)

**背景混合模式属性**定义元素的背景图像应该如何相互混合以及如何与元素的背景颜色混合。

**语法:**

```html
background-blend-mode: normal|multiply|screen|darken|lighten|
color-dodge|saturation|difference|luminosity|overlay;
```

**默认值:**

*   **正常**

**属性:**
**正常:**这是默认值。它将混合模式设置为正常。

*   **语法:**

```html
background-blend-mode: normal;
```

*   **示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <title>background-blend-mode Property</title>
    <style>
        #myDIV {
            width: 400px;
            height: 299px;
            background-color: green;
            background-repeat: no-repeat;
            background-image:
url("https://media.geeksforgeeks.org/wp-content/uploads/geeksforgeeks-logo.png");
            background-blend-mode: normal;
            background-size: contain;
        }
    </style>
</head>

<body>
    <div id="myDIV"></div>
</body>

</html>
```

*   **输出:**

![](img/69e078b3ee9d33feb8fbddc17cdbc01a.png)

**乘法:**设置混合模式为乘法。这导致图像比以前更暗。

*   **语法:**

```html
background-blend-mode: multiply;
```

*   **示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <title>background-blend-mode Property</title>
    <style>
        #myDIV {
            width: 400px;
            height: 299px;
            background-color: green;
            background-repeat: no-repeat;
            background-image:
url("https://media.geeksforgeeks.org/wp-content/uploads/geeksforgeeks-logo.png");
            background-blend-mode: multiply;
            background-size: contain;
        }
    </style>
</head>

<body>
    <div id="myDIV"></div>
</body>

</html>
```

*   **输出:**

![](img/2c59366f4c884be7efed10600c40ef74.png)

**屏幕:**设置混合模式为屏幕。在这种模式下，图像和颜色都被反转、相乘然后反转。又来了。

*   **语法:**

```html
background-blend-mode: screen;
```

*   **示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <title>background-blend-mode Property</title>
    <style>
        #myDIV {
            width: 400px;
            height: 299px;
            background-color: green;
            background-repeat: no-repeat;
            background-image:
url("https://media.geeksforgeeks.org/wp-content/uploads/geeksforgeeks-logo.png");
            background-blend-mode: screen;
            background-size: contain;
        }
    </style>
</head>

<body>
    <div id="myDIV"></div>
</body>

</html>
```

*   **输出:**

![](img/c39c79023b689c667b20f66c0589cfa4.png)

**变暗:**将混合模式设置为变暗。在这种模式下，如果背景图像比背景颜色暗，则图像被替换，否则，图像保持原样。

*   **语法:**

```html
background-blend-mode: darken;
```

*   **示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <title>background-blend-mode Property</title>
    <style>
        #myDIV {
            width: 400px;
            height: 299px;
            background-color: green;
            background-repeat: no-repeat;
            background-image:
url("https://media.geeksforgeeks.org/wp-content/uploads/geeksforgeeks-logo.png");
            background-blend-mode: darken;
            background-size: contain;
        }
    </style>
</head>

<body>
    <div id="myDIV"></div>
</body>

</html>
```

*   **输出:**

![](img/c04c478a3f211eb777914a78a90c1dae.png)

**变亮:**设置混合模式变亮。在这种模式下，如果背景图像比背景颜色浅，则图像被替换，否则，图像保持原样。

*   **语法:**

```html
background-blend-mode: lighten;
```

*   **示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <title>background-blend-mode Property</title>
    <style>
        #myDIV {
            width: 400px;
            height: 299px;
            background-color: green;
            background-repeat: no-repeat;
            background-image:
url("https://media.geeksforgeeks.org/wp-content/uploads/geeksforgeeks-logo.png");
            background-blend-mode: lighten;
            background-size: contain;
        }
    </style>
</head>

<body>
    <div id="myDIV"></div>
</body>

</html>
```

*   **输出:**

![](img/025f40a22589cb5ad4120a67495d00a7.png)

**颜色-减淡:**设置混合模式为颜色-减淡。在这种模式下，背景色被背景图像的反转所分割。这与屏幕混合模式非常相似。

*   **语法:**

```html
background-blend-mode: color-dodge;
```

*   **示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <title>background-blend-mode Property</title>
    <style>
        #myDIV {
            width: 400px;
            height: 299px;
            background-color: green;
            background-repeat: no-repeat;
            background-image:
url("https://media.geeksforgeeks.org/wp-content/uploads/geeksforgeeks-logo.png");
            background-blend-mode: color-dodge;
            background-size: contain;
        }
    </style>
</head>

<body>
    <div id="myDIV"></div>
</body>

</html>
```

*   **输出:**

![](img/3a90cef77df53a0efd8d30a6615d0984.png)

**饱和度:**设置混合模式变亮。该模式保持背景图像的饱和度，同时混合背景颜色的色调和亮度。

*   **语法:**

```html
background-blend-mode: saturation;
```

*   **示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <title>background-blend-mode Property</title>
    <style>
        #myDIV {
            width: 400px;
            height: 299px;
            background-color: green;
            background-repeat: no-repeat;
            background-image:
url("https://media.geeksforgeeks.org/wp-content/uploads/geeksforgeeks-logo.png");
            background-blend-mode: saturation;
            background-size: contain;
        }
    </style>
</head>

<body>
    <div id="myDIV"></div>
</body>

</html>
```

*   **输出:**

![](img/52241c8d3cb9da6d1a76a54b1e424b5b.png)

**差异:**设置混合模式为差异。该模式是从最亮的背景图像中减去较暗的背景图像颜色和背景颜色的结果。通常图像会有很高的对比度。

*   **语法:**

```html
background-blend-mode: difference;
```

*   **示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <title>background-blend-mode Property</title>
    <style>
        #myDIV {
            width: 400px;
            height: 299px;
            background-color: green;
            background-repeat: no-repeat;
            background-image:
url("https://media.geeksforgeeks.org/wp-content/uploads/geeksforgeeks-logo.png");
            background-blend-mode: difference;
            background-size: contain;
        }
    </style>
</head>

<body>
    <div id="myDIV"></div>
</body>

</html>
```

*   **输出:**

![](img/0e1d35633a330fe2c1d76a926565ca58.png)

**光度:**将混合模式设置为光度。在这种模式下，顶部颜色的亮度被保留，同时使用背景颜色的饱和度和色调。

*   **语法:**

```html
background-blend-mode: luminosity;
```

*   **示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <title>background-blend-mode Property</title>
    <style>
        #myDIV {
            width: 400px;
            height: 299px;
            background-color: green;
            background-repeat: no-repeat;
            background-image:
url("https://media.geeksforgeeks.org/wp-content/uploads/geeksforgeeks-logo.png");
            background-blend-mode: luminosity;
            background-size: contain;
        }
    </style>
</head>

<body>
    <div id="myDIV"></div>
</body>

</html>
```

*   **输出:**

![](img/4cf4ce14029ccd400021a57e7a7ec65f.png)

**叠加:**设置混合模式为叠加。在这种模式下，背景色与背景图像混合，以反映背景的亮度或暗度。

*   **语法:**

```html
background-blend-mode: Overlay;
```

*   **示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <title>background-blend-mode Property</title>
    <style>
        #myDIV {
            width: 400px;
            height: 299px;
            background-color: green;
            background-repeat: no-repeat;
            background-image:
url("https://media.geeksforgeeks.org/wp-content/uploads/geeksforgeeks-logo.png");
            background-blend-mode: overlay;
            background-size: contain;
        }
    </style>
</head>

<body>
    <div id="myDIV"></div>
</body>

</html>
```

*   **输出:**

![](img/0bdf676c4ebc71a7a45e322ef664d8c5.png)

**支持的浏览器:***背景混合模式*属性支持的浏览器如下:

*   谷歌 Chrome 35.0
*   Firefox 30.0
*   Opera 22.0
*   苹果 Safari 7.1