# SVG 点数属性

> 原文:[https://www.geeksforgeeks.org/svg-pointsaty-attribute/](https://www.geeksforgeeks.org/svg-pointsaty-attribute/)

*点*属性表示光源指向的点的 *<【滤镜】>* 元素上的属性*原始单位*建立的坐标系中的 y 位置。只有 *< feSpotLight >* 元素在使用这个属性。

**语法:**

```html
pointsAtY = number
```

**属性值:***点*属性接受上面提到的和下面描述的值

*   **数字:**是指当前坐标系单位的数值。它的默认值被认为是 0。

下面的例子说明了*点*属性的使用。

**例 1:**

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

**例 2:**

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