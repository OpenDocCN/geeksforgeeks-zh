# SVG 关键时间属性

> 原文:[https://www.geeksforgeeks.org/svg-keytimes-attribute/](https://www.geeksforgeeks.org/svg-keytimes-attribute/)

*关键时间*属性用于指定 0 到 1(包括 0 和 1)之间的浮点数(时间值)列表，该列表用于控制动画的速度。使用该属性的元素包括 *<动画>、<动画生态师>、<动画情感>、*和 *<动画转换>。*

**语法:**

```html
keyTimes = [;<number>]*
```

**属性值:***关键时间*属性接受上面提到的和下面描述的值。

*   **【；<数字> ]*:** 这是一个由分号分隔的 0 到 1 之间的数字列表。

**注意:***关键时刻*属性的默认值为*无*

下面的例子说明了*键时间*属性的使用。

**例 1:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<body>
    <h1 style="color: green; margin-left: 35px;">
        GeeksforGeeks
    </h1>

    <svg viewBox="-10 80 620 120" 
        xmlns="http://www.w3.org/2000/svg">

        <polygon fill="green" points="55.724, 
            91.297 41.645, 91.297 36.738, 
            105.038 47.483, 105.038 41.622,
            124.568 62.783, 98.526 51.388, 
            98.526" />

        <animate attributeType="CSS" 
            attributeName="visibility" 
            values="hidden;visible;hidden" 
            keyTimes="0; 0.75; 1" dur="1s" 
            repeatCount="indefinite" />
    </svg>
</body>

</html>
```

**输出:**

![](img/d865c04be40c322489d93613550e369e.png)

**例 2:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<body>
    <h1 style="color: green; margin-left: 35px;">
        GeeksforGeeks
    </h1>

    <svg viewBox="0 0 620 120" 
        xmlns="http://www.w3.org/2000/svg">

        <circle cx="60" cy="10" r="10" fill="green">
            <animate attributeName="cx" dur="2s" 
                repeatCount="indefinite" 
                values="60 ; 110 ; 60 ; 10 ; 60"
                keyTimes="0 ; 0.3 ; 0.6 ; 0.80 ; 1" />
        </circle>
    </svg>
</body>

</html>
```

**输出:**

![](img/04db8608525b4f3e12882ecc1ce8d9e3.png)