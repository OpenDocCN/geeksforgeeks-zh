# SVG 变换属性

> 原文：`https://www.geeksforgeeks.org/svg-transform-attribute/`

`transform`属性表示应用于元素及其子元素的变换定义列表。在 SVG 1.1 中，只允许这些元素使用变换属性：`<a>`、`<circle>`、`<clip path>`、`<defs>`、`<ellipse>`、`<foreignObject>`、`<g>`、`<image>`、`<line>`、`<path>`、`<polygon>`。

### 语法

```html
transform = scale() | translate() | rotate() | 
                 matrix() | skewX() | skewY()
```

### 属性值

`transform`属性接受上面提到的和下面描述的变换函数。

*   **`skewX()`:** 它列举了一个沿 x 轴倾斜一个角度的倾斜变换。
*   **`skewY()`:** 它列举了一个沿 y 轴倾斜一个角度的倾斜变换。
*   **`scale()`:** 通过 x 和 y 枚举一个 scale 操作，如果不提供 y，则假设等于 x。
*   **`rotate()`:** 它列举了围绕给定点旋转一个角度。
*   **`translate()`:** 它将对象移动 x 和 y，如果不提供 y，则假定为 0。
*   **`matrix()`:** 它以六值变换矩阵的形式枚举一个变换。

### 示例 1

以下示例说明了使用`rotate()`、`translate()`、`skewX()`和`scale()`变换函数来使用`transform`属性。

```html
<!DOCTYPE html>
<html>

<body>
    <h1 style="color:green; font-size:50px;">
        GeeksforGeeks
    </h1>

<svg viewBox="-25 0 450 400" 
        xmlns="http://www.w3.org/2000/svg" 
        xmlns:xlink="http://www.w3.org/1999/xlink">

<g fill="grey" transform="rotate(-10 50 100)
                        translate(-36 45.5)
                        skewX(40)
                        scale(1 0.5)">
            <path id="heart" d="M 10, 30 A 20, 20 
                            0, 0, 1 50, 30 A 20, 
                            20 0, 0, 1 90, 30 Q 90,
                            60 50, 90 Q 10, 60 10, 
                            30 z" />
        </g>

<use xlink:href="#heart" 
            fill="none" stroke="green" />
    </svg>

</body>

</html>
```

**输出:**

![](img/e04af63beffdd0e00dcc847c1facfc9c.png)

### 示例 2

以下是使用`scale()`变换功能说明`transform`属性使用的示例。

```html
<!DOCTYPE html>
<html>

<body>
    <h1 style="color:green; font-size:50px;">
        GeeksforGeeks
    </h1>

<svg viewBox="-60 -40 400 400" 
        xmlns="http://www.w3.org/2000/svg">

<circle cx="0" cy="0" r="10" 
            fill="green" transform="scale(4)" />

<circle cx="0" cy="0" r="10" 
            fill="yellow" transform="scale(1, 4)" />

<circle cx="0" cy="0" r="10" 
            fill="lightgreen" transform="scale(4, 1)" />

<circle cx="0" cy="0" r="10" fill="green" />
    </svg>
</body>

</html>
```

**输出:**

![](img/b8f47ec1e609d5822c2d229b5fe8bb0f.png)