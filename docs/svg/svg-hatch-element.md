# SVG `<hatch>`元素

> 原文:[https://www.geeksforgeeks.org/svg-hatch-element/](https://www.geeksforgeeks.org/svg-hatch-element/)

SVG 代表可缩放矢量图形。它可以用来制作像在 HTML 画布中的图形和动画。

**<阴影>** SVG 元素用于描摹对象。它使用一个或多个预定义的路径来填充对象。它在指定方向上以固定间隔重复路径，以覆盖要绘制的区域。

**语法:**

```html
<hatch x="" y="" pitch="" rotate="" hatchUnits="" 
hatchContentUnits="" transform="" href="">

```

**属性:**

*   **x**–定义用户坐标系中的 x 轴坐标。
*   **y**–定义用户坐标系中的 y 轴坐标。
*   **旋转–**它指定动画元素沿着<动画情感>元素中指定的路径移动时如何旋转。
*   **变换–**它定义了应用于元素及其子元素的变换定义列表。
*   **href–**它将资源链接定义为引用网址。

**例 1:**

```html
<!DOCTYPE html>
<html>

<body>
    <svg viewBox="0 0 1100 400">
        <defs>
            <hatch id="hatch" 
                hatchUnits="userSpaceOnUse" 
                pitch="5" rotate="135">

                <hatchpath stroke="#a080ff" 
                    stroke-width="2" />
            </hatch>
        </defs>

        <foreignObject x="95" y="12" 
            width="160" height="160" 
            color="Green">

            <div>
                <br><br>GEEKSFORGEEKS<br><br>
            </div>

        </foreignObject>
        <rect fill="url(#hatch)" 
            stroke="Green" stroke-width="2" 
            x="5%" y="5%" width="20%" 
            height="20%" />
    </svg>
</body>

</html>
```

**输出:**

![](img/79b2edf0950ddb00fbb187814dc9298e.png)

**例 2:**

```html
<!DOCTYPE html>
<html>

<body>
    <svg viewBox="0 0 1100 400">
        <defs>
            <hatch id="hatch" 
                hatchUnits="userSpaceOnUse" 
                pitch="9" rotate="135">

                <hatchpath stroke="Green" 
                    stroke-width="12" />
            </hatch>
        </defs>

        <foreignObject x="110" y="12" 
            width="160" height="160" 
            color="Green">

            <div>
                <br><br>GeeksForGeeks<br><br>
            </div>

        </foreignObject>
        <ellipse vfill="url(#hatch)" 
            fill="None" stroke="green" 
            stroke-width="2" cx="164" 
            cy="58" rx="100" ry="50"
            fill />
    </svg>
</body>

</html>
```

**输出:**

![](img/0dc2c62317900bef7fb2a1eb2c95b5da.png)