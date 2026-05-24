# CSS 伸缩属性

> 原文:[https://www.geeksforgeeks.org/css-flex-property/](https://www.geeksforgeeks.org/css-flex-property/)

flex CSS [简写属性](https://www.geeksforgeeks.org/css-shorthand-properties/)是 flex-grow、flex-short 和 flex-base 属性的组合。用于设置柔性物品的长度。flex 属性响应速度快，对移动设备友好。定位子元素和主容器很容易。页边距不会随着内容页边距而折叠。无需编辑 HTML 部分，任何元素的顺序都可以轻松更改。

**语法:**

```html
flex: flex-grow flex-shrink flex-basis|auto|initial|inherit;
```

**属性值:**

*   [**【灵活增长属性】**](https://www.geeksforgeeks.org/css-flex-grow-property/) **:** 一个数字，指定相对于其余灵活项目，项目将增长多少。
*   [**【伸缩属性:**](https://www.geeksforgeeks.org/css-flex-shrink-property/) 一个数字，它指定了相对于其他灵活项目，项目会缩小多少。
*   [**【弹性基属性:**](https://www.geeksforgeeks.org/css-flex-basis-property/) 设置项目长度。flex-basis 的合法值是:auto、inherit 或后跟% em、px 或任何其他长度单位的数字。
    *   [**折曲属性:**](https://www.geeksforgeeks.org/css-flex-wrap-property/)CSS 折曲属性用于指定折曲项是强制成单行还是折多行。

可以借助 1、2 或 3 个值来指定 flex 属性:

*   **单值语法:**该值应包含以下内容之一:
    *   [**号**](https://www.geeksforgeeks.org/css-number-data-type/) **:** 如果表示为 *flex: <号>1 0；*则伸缩、伸缩基的值分别为 1 & 0。
    *   可以通过其中一个关键字指定为 *auto，none* 或 *initial。*
*   **双值语法:**必须包含以下值:
    *   第一个值应该是*数字*，它将代表伸缩增长。
    *   第二个值应包含以下内容之一:
        *   **数字:**如果是数字，则表示为伸缩。
        *   a [*宽度*](https://www.geeksforgeeks.org/css-width-property/) 用有效值将代表 flex-basis。
*   **三值语法:**值的顺序应该相同:
    *   第一个数字代表灵活增长。
    *   第二个数字代表伸缩收缩。
    *   带有有效值的*宽度*将代表弹性基。

**示例:**本示例借助单个值来描述 flex 属性，以表示 flex。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <title> CSS flex Property </title>
    <style>
    #Geeks {
        width: 300px;
        height: 200px;
        border: 1px solid black;
        display: flex;
    }

    #Geeks div {
        flex: 1;
    }

    .GFG1 {
        background-color: green;
    }

    .GFG2 {
        background-color: lightgreen;
    }

    .GFG3 {
        background-color: darkgreen;
    }
    </style>
</head>

<body>
    <h2>CSS flex Property</h2>
    <div id="Geeks">
        <div class="GFG1"> GeeksforGeeks </div>
        <div class="GFG2"> Lite Content </div>
        <div class="GFG3"> Special Content </div>
    </div>
</body>

</html>
```

**输出:**

![](img/732826785465bcab0f1b46dfcc8bdaf4.png)

**示例 2:** 本示例借助 3 个值来描述伸缩属性，这 3 个值代表伸缩增长、伸缩收缩&的伸缩基础属性。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <title> CSS flex Property </title>
    <style>
    #Geeks {
        width: 300px;
        height: 200px;
        border: 1px solid black;
        display: flex;
    }

    #Geeks div {
        flex: 1 0 auto;
    }

    .GFG1 {
        background-color: green;
    }

    .GFG2 {
        background-color: lightgreen;
    }

    .GFG3 {
        background-color: darkgreen;
    }
    </style>
</head>

<body>
    <h2>CSS flex Property</h2>
    <div id="Geeks">
        <div class="GFG1"> GeeksforGeeks </div>
        <div class="GFG2"> Lite Content </div>
        <div class="GFG3"> Special Content </div>
    </div>
</body>

</html>
```

**输出:**

![](img/c5465641e63d848e752912ecb074645a.png)

**支持的浏览器:**

*   谷歌 Chrome 29.0，21.0 -webkit-
*   微软边缘 12.0，12.0-网络工具包-
*   Internet Explorer 11.0，10.0 -ms-
*   火狐 28.0， 18.0 -moz-
*   Safari 9.0，6.1 -webkit-
*   Opera 17.0