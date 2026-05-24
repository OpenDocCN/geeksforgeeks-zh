# SVG point satx 属性

> 原文:[https://www.geeksforgeeks.org/svg-pointsatx-attribute/](https://www.geeksforgeeks.org/svg-pointsatx-attribute/)

*点 sAtX* 属性表示光源指向的点的 *<【滤镜】>* 元素上的 *primitiveUnits* 属性建立的坐标系中的 x 位置。只有< *feSpotLight* >元素在使用这个属性。

**语法:**

```html
pointsAtX = number
```

**属性值:***点 sAtX* 属性接受上面提到的和下面描述的值:

*   **数字:**是指当前坐标系单位的数值。它的默认值被认为是 0。

下面的例子说明了*点 sAtX* 属性的使用。

**例 1:**

```html
<!DOCTYPE html>
<html>

<body>
    <div style="color: green;">

        <h1>GeeksforGeeks</h1>

        <svg viewBox="-10 0 1120 200" 
            xmlns="http://www.w3.org/2000/svg">

            <filter id="Geek1" x="0.01" 
                width="100%" height="100%">

                <feDiffuseLighting in="SourceGraphic">
                    <feSpotLight x="50" y="50" 
                        z="60" pointsAtX="0" />
                </feDiffuseLighting>
            </filter>

            <rect width="200" height="200" 
                style="filter: url(#Geek1);" />
        </svg>
    </div>
</body>

</html>
```

**输出:**

![](img/28f9b452593d6f640fad5f03019435f3.png)

**例 2:**

```html
<!DOCTYPE html>
<html>

<body>
    <div style="color: green;">

        <h1>GeeksforGeeks</h1>

        <svg viewBox="-10 0 1120 200" 
            xmlns="http://www.w3.org/2000/svg">

            <filter id="geek2" x="0.01" 
                width="100%" height="100%">

                <feDiffuseLighting in="SourceGraphic">
                    <feSpotLight x="60" y="60" 
                        z="50" pointsAtX="400" />
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

![](img/64b7f45761b91514c400b3ffc405222e.png)