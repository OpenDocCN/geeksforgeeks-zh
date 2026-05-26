# SVG `patternContentUnits` 属性

> 原文: [https://www.geeksforgeeks.org/svg-patterncontentunits-attribute/](https://www.geeksforgeeks.org/svg-patterncontentunits-attribute/)

`patternContentUnits` 属性用于指示 `<pattern>` 元素的内容必须使用哪个坐标系。

**语法:**

```html
patternContentUnits = "userSpaceOnUse"

// Or

patternContentUnits = "objectBoundingBox"
```

**属性值:**
`patternContentUnits` 属性接受上述值，如下所述:

*   **`userSpaceOnUse`**: 表示 `<pattern>` 元素内的所有坐标都是指创建图案拼贴时定义的用户坐标系。
*   **`objectBoundingBox`**: 表示 `<pattern>` 元素内的所有坐标都是 `<pattern>` 元素边界框的分数或百分比值。

**注意:** 默认值为 `userSpaceOnUse`。

**示例 1:** 以下是使用 `objectBoundingBox` 值说明 `patternContentUnits` 属性使用的示例。

## HTML

```html
<!DOCTYPE html>
<html>

<body>
    <h1 style="color: green; 
        margin-left: 2%;">
        GeeksforGeeks
    </h1>

<svg viewBox="0 0 300 200" 
        xmlns="http://www.w3.org/2000/svg">

<pattern id="geek2" width="40%" 
            height="40%" fill="green" 
            patternContentUnits="objectBoundingBox">

<ellipse cx=".2" cy=".1" rx=".2" ry=".1" />
        </pattern>

<rect width="50" height="50" 
            fill="url(#geek2)" />
    </svg>
</body>

</html>
```

**输出:** 以下是对应上述代码生成的输出

![](img/389d67d50a9e4c6891ad5e0909f0fd31.png)

**示例 2:** 以下是使用 `userSpaceOnUse` 值说明 `patternContentUnits` 属性使用的示例。

## HTML

```html
<!DOCTYPE html>
<html>

<body>
    <h1 style="color: green;">
        GeeksforGeeks
    </h1>

<svg viewBox="0 0 200 200" 
        xmlns="http://www.w3.org/2000/svg">

<pattern id="geek2" width="40%" 
            height="40%" fill="green" 
            patternContentUnits="userSpaceOnUse">

<ellipse cx="5" cy="5" rx="2" ry="1" />
        </pattern>

<rect width="50" height="50" 
            fill="url(#geek2)" />
    </svg>
</body>

</html>
```

**输出:** 以下是对应上述代码生成的输出

![](img/10326482c5cb0b88cd4210dd724e84a3.png)