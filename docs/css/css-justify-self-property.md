# CSS 自圆其说属性

> 原文:[https://www.geeksforgeeks.org/css-justify-self-property/](https://www.geeksforgeeks.org/css-justify-self-property/)

**自对齐**属性用于指定内容位置与 CSS 网格中适当轴的对齐方式。

**语法:**

> 自圆其说:拉伸|正常|自动|基线|开始|结束|中心|伸缩-开始|伸缩-结束|自启动|自结束|左|右|安全|不安全

**属性值:**

*   **拉伸:**是该属性的默认值，它使内容填充单元格的整个宽度。
*   **normal:** 它是琐碎属性，即在块级布局中表现为 ***开始*** 并在替换的绝对定位框中表现为 ***拉伸*** 在其他绝对定位框中，在表格和 flex 布局中，它被忽略，在网格布局中表现为拉伸，除了在少数情况下，如具有纵横比的框中，它充当 ***开始*** 值。
*   **自动:**它是用于调整位于父元素中的项目属性的值，或者默认为 ***正常的*** 值。这是默认值。
*   **基线**:将当前框的第一个或最后一个基线集的对齐基线对齐到其基线共享组中所有框的共享的第一个或最后一个基线集中的对应基线。 ***第一个基线*** 的回退值是 ***开始*** ，最后一个基线 的回退值是 ***结束。***
*   **开始**:允许内容自身对齐单元格左侧。
*   **end:** 它允许内容自身对齐单元格右侧。
*   **居中**:允许内容自身对齐单元格中心。
*   **伸缩启动:**与**启动**值相同。
*   **伸缩端:**与**端**值相同。
*   **自启动:**它在项目开始时将项目对齐对齐容器的左侧。
*   **自结束:**它将项目对齐到项目末尾对齐容器的右侧。
*   **左侧:**使物品包与对齐容器左侧齐平。如果该属性的轴与内联轴不平行，则它的作用与 ***开始*** 相同。
*   **右侧:**它使物品包与对齐容器的右侧齐平。如果该属性的轴与内联轴不平行，则它的作用与 ***端*** 相同。
*   **安全:**如果物品溢出对齐容器，则使物品对齐为 ***开始*** 值。
*   **不安全:**它使物品按照给定值对齐，而不管对齐容器和物品的相对大小。

**示例 1:** 在此示例中，自圆其说不用于对齐。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <style>
        article {
            font-family: sans-serif;
            background-color: green;
            display: grid;
            grid-template-columns: 1fr 1fr;
            grid-auto-rows: 70px;
            grid-gap: 30px;
            width: 700px;
            justify-items: stretch;
            border: solid;
            margin: 20%;
        }

        article span {
            background-color: white;
            color: green;
            margin: 2px;
            text-align: center;
            border: solid;
        }

        article,
        span {
            padding: 5px;
            border-radius: 3px;
            border: solid;
        }
    </style>
</head>

<body>
    <article class="container">
        <span>GEEKS</span>
        <span>FOR</span>
        <span>GEEKS</span>
        <span>ONLINE</span>
        <span>PORTAL</span>
    </article>
</body>

</html>
```

**输出:**

![](img/deda2400f7c1045cccbf2e87fdc54af6.png)

**示例 2:** 在此示例中，一些自调整值用于对齐。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <style>
        article {
            font-family: sans-serif;
            background-color: green;
            display: grid;
            grid-template-columns: 1fr 1fr;
            grid-auto-rows: 70px;
            grid-gap: 30px;
            width: 700px;
            justify-items: stretch;
            border: solid;
            margin: 20%;
        }

        span:nth-child(2) {
            justify-self: start;
        }

        span:nth-child(3) {
            justify-self: center;
        }

        span:nth-child(4) {
            justify-self: end;
        }

        article span {
            background-color: white;
            color: green;
            margin: 2px;
            text-align: center;
            border: solid;
        }

        article,
        span {
            padding: 5px;
            border-radius: 3px;
            border: solid;
        }
    </style>
</head>

<body>
    <article class="container">
        <span>GEEKS</span>
        <span>FOR</span>
        <span>GEEKS</span>
        <span>ONLINE</span>
        <span>PORTAL</span>
    </article>
</body>

</html>
```

**输出:**

![](img/6a6de5c30dff4d166042026618561471.png)

**支持的浏览器:**

*   谷歌 Chrome
*   火狐浏览器
*   歌剧
*   苹果 Safari