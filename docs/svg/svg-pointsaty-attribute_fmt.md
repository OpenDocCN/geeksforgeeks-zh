# SVG `pointsAtY`属性

> 原文: [https://www.geeksforgeeks.org/svg-pointsaty-attribute/](https://www.geeksforgeeks.org/svg-pointsaty-attribute/)

`pointsAtY`属性表示在`<feSpotLight>`元素上使用的、基于`primitiveUnits`属性建立的坐标系中，光源指向点的y位置。

## 语法

```html
pointsAtY = number
```

## 属性值

`pointsAtY`属性接受一个数值。

*   **数值**: 表示当前坐标系单位的数值。其默认值为`0`。

下面的例子说明了`pointsAtY`属性的使用。

## 例 1

```html
<!DOCTYPE html>
<html>

<body>
    <div style="color: green;">

<h1>GeeksforGeeks</h1>

<svg viewBox="0 0 1120 200" 
            xmlns="http://www.w3.org/2000/svg">

<filter id="geek1" width="100%" 
                height="100%">

<feDiffuseLighting in="SourceGraphic">
                    <feSpotLight x="50" y="50" 
                        z="60" pointsAtY="0" />
                </feDiffuseLighting>
            </filter>

<rect width="200" height="200" 
                style="filter: url(#geek1);" />
        </svg>
    </div>
</body>

</html>
```

**输出:**

![](img/b48caf6722da66e64dd527229792dbcd.png)

## 例 2

```html
<!DOCTYPE html>
<html>

<body>
    <div style="color: green;">

<h1>GeeksforGeeks</h1>

<svg viewBox="0 0 1120 200" 
            xmlns="http://www.w3.org/2000/svg">

<filter id="geek2" width="100%" 
                height="100%">

<feDiffuseLighting in="SourceGraphic">
                    <feSpotLight x="50" y="50" 
                        z="60" pointsAtY="500" />
                </feDiffuseLighting>
            </filter>

<rect width="200" height="200" 
                style="filter: url(#geek2);" />
        </svg>
    </div>
</body>

</html>
```

**输出:**

![](img/aca7d69443dd1c1b914553ac4447a25e.png)