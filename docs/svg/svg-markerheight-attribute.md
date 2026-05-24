# SVG 标记高度属性

> 原文:[https://www.geeksforgeeks.org/svg-markerheight-attribute/](https://www.geeksforgeeks.org/svg-markerheight-attribute/)

*标记灯*属性表示视口的高度，当根据保留光谱比和视图框属性显示时， *<标记>* 将被拟合到该视口中。只有 *<标记>* 元素在使用这个属性。

**语法:**

```html
markerrHeight = "length-percentage" | "number"
```

**属性值:***标记灯*属性接受上面提到的和下面描述的值。

*   **长度百分比:**表示标记的相对高度或绝对高度。
*   **数字:**表示标记的高度，单位由*标记其*属性定义。

**注意:***标记灯*属性默认值为 3。

**示例 1:** 以下是说明*标记*属性使用的示例。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

    <body>
        <h1 style="color: green; 
            margin-left: 10px;">
            GeeksforGeeks
        </h1>

        <svg viewBox="0 15 1220 520" 
             xmlns="http://www.w3.org/2000/svg">
            <defs>
                <marker id="geek"
                    viewBox="0 0 10 10"
                    refX="1" refY="5"
                    markerUnits="strokeWidth"
                    markerWidth="8"
                    markerHeight="8"
                    orient="auto">
                   <path d="M 0 0 L 10 5 L 0 10 z" 
                    fill="#008000"/>
                </marker>
            </defs>

            <polyline points="20, 20 40, 25 60,
                    40 80, 120 120, 140 200, 180"
                    style="fill:none;stroke:green;
                    stroke-width:5" 
                    marker-end="url(#geek)"/>
          </svg>
    </body>

</html>
```

**输出:**

![](img/6987065e2d549322ca1eb970fdcc87dd.png)

**例 2:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

    <body>
        <h1 style="color: green; 
            margin-left: 10px;">
            GeeksforGeeks
        </h1>

        <svg viewBox="0 15 1220 520" 
             xmlns="http://www.w3.org/2000/svg">
            <defs>
                <marker id="geek"
                    viewBox="0 0 10 10"
                    refX="1" refY="5"
                    markerUnits="strokeWidth"
                    markerWidth="8"
                    markerHeight="8"
                    orient="auto">
                   <path d="M 0 0 L 10 5 L 0 10 z" 
                    fill="#008000"/>
                </marker>
            </defs>

            <polyline points="100, 105 180,
                    20 100, 17 50, 100"
                    stroke="green" 
                    stroke-width="5" 
                    fill ="none"
                    marker-end="url(#geek)"/>
          </svg>
    </body>

</html>
```

**输出:**

![](img/b7da3add6ee1c31edb09e4e8092919b4.png)