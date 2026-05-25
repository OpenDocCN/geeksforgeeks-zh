# HTML | DOM Style columnRuleColor 属性

> 原文: [https://www.geeksforgeeks.org/html-dom-style-columnrulecolor-property/](https://www.geeksforgeeks.org/html-dom-style-columnrulecolor-property/)

**DOM Style columnRuleColor** 属性指定列间规则的颜色。

## 语法

*   用于设置 `columnRuleColor` 属性:
    ```html
    object.style.columnRuleColor = "color|initial|inherit"
    ```

*   返回 `columnRuleColor` 属性:
    ```html
    object.style.columnRuleColor
    ```

## 属性值

*   `color`: 用于指定规则的颜色。
*   `initial`: 用于设置默认值。
*   `inherit`: 用于从父元素继承属性。

## 返回值
返回代表元素的列规则颜色属性的单个字符串。

### 1. Color
This specifies the color of the rule.

**Example-1:**
```html
<!DOCTYPE html>
<html>
<head>
    <title>
        HTML | DOM Style columnRuleColor Property
    </title>
    <style>
        #myDIV {
            width: 90%;
            height: 70%;
            border: 2px solid green;
            padding: 10px;
            column-count: 3;
            column-rule: 3px outset red;
        }
        #p1 {
            font-size: 20px;
            color: green;
        }
    </style>
</head>
<body>
<div id="myDIV">
    <p id="p1">
        <u>Welcome to GeeksforGeeks.!</u>
    </p>
    <p>
        Computer Science is the study of computers and computational systems. Unlike electrical and computer engineers, computer scientists deal mostly with software and software systems; this includes their theory, design, development, and application. Principal areas of study within Computer Science include artificial intelligence, computer systems and networks, security, database systems, human computer interaction, vision and graphics, numerical analysis, programming languages, software engineering, bioinformatics and theory of computing. Although knowing how to program is essential to the study of computer science, it is only one element of the field. Computer scientists design and analyze algorithms to solve programs and study the performance of computer hardware and software. The problems that computer scientists encounter range from the abstract-- determining what problems can be solved with computers and the complexity of the algorithms that solve them – to the tangible – designing applications that perform well on handheld devices, that are easy to use, and that uphold security measures.
    </p>
</div>
<br>
<input type="button" onclick="mainFunction()" value="Submit" />
<script>
    function mainFunction() {
        // Define color.
        document.getElementById("myDIV").style.columnRuleColor = "green";
    }
</script>
</body>
</html>
```

**输出:**

**点击前:**
![](img/5a28e918f7257f5e00767b1f6c3e988c.png)

**点击后:**
![](img/6a4dfeb3aea7c7886a66a49c6d046a7c.png)

### 2. initial
This set the color of the rule to the `initial`. By default it is black.

**Example-2:**
```html
<!DOCTYPE html>
<html>
<head>
    <title>
        HTML | DOM Style columnRuleColor Property
    </title>
    <style>
        #myDIV {
            width: 90%;
            height: 70%;
            border: 2px solid green;
            padding: 10px;
            column-count: 3;
            column-rule: 3px outset red;
        }
        #p1 {
            font-size: 20px;
            color: green;
        }
    </style>
</head>
<body>
<div id="myDIV">
    <p id="p1">
        <u>Welcome to GeeksforGeeks.!</u>
    </p>
    <p>
        Computer Science is the study of computers and c omputational systems. Unlike electrical and computer engineers, computer scientists deal mostly with software and software systems; this includes their theory, design, development, and application. Principal areas of study within Computer Science include artificial intelligence, computer systems and networks, security, database systems, human computer interaction, vision and graphics, numerical analysis, programming languages, software engineering, bioinformatics and theory of computing. Although knowing how to program is essential to the study of computer science, it is only one element of the field. Computer scientists design and analyze algorithms to solve programs and study the performance of computer hardware and software. The problems that computer scientists encounter range from the abstract-- determining what problems can be solved with computers and the complexity of the algorithms that solve them – to the tangible – designing applications that perform well on handheld devices, that are easy to use, and that uphold security measures.
    </p>
</div>
<br>
<input type="button" onclick="mainFunction()" value="Submit" />
<script>
    function mainFunction() {
        // Set column color.
        document.getElementById("myDIV").style.columnRuleColor = "initial";
    }
</script>
</body>
</html>
```

**输出:**

**点击前:**
![](img/5a28e918f7257f5e00767b1f6c3e988c.png)

**点击后:**
![](img/ba17709b2e4f6d0da1380421fd6b5c7e.png)

### 3. inherit
This inherits this property from its parent element. This mean that this will make the same color as of the color of the parent element.

**Example-3:**
```html
<!DOCTYPE html>
<html>
<head>
    <title>
        HTML | DOM Style columnRuleColor Property
    </title>
    <style>
        #myDIV {
            width: 90%;
            height: 70%;
            border: 2px solid green;
            padding: 10px;
            color: red;
            column-count: 3;
            column-rule: 3px solid green;
        }
        #p1 {
            font-size: 20px;
            color: green;
        }
    </style>
</head>
<body>
<div id="myDIV">
    <p id="p1">
        <u>Welcome to GeeksforGeeks.!</u>
    </p>
</div>
```

# 计算机科学概述

计算机科学是研究计算机和计算系统的学科。与电气和计算机工程师不同，计算机科学家主要处理软件和软件系统；这包括其理论、设计、开发和应用。计算机科学内的主要研究领域包括人工智能、计算机系统与网络、安全、数据库系统、人机交互、视觉与图形学、数值分析、编程语言、软件工程、生物信息学和计算理论。虽然知道如何编程对于计算机科学的学习至关重要，但它只是该领域的一个组成部分。计算机科学家设计和分析算法以解决问题，并研究计算机硬件和软件的性能。计算机科学家遇到的问题范围广泛，从抽象的——确定哪些问题可以用计算机解决以及解决它们的算法的复杂性——到具体的——设计在手持设备上运行良好、易于使用并遵守安全措施的应用程序。

## 脚本函数

```javascript
function mainFunction() {
    //  Set color using inherit.
    document.getElementById(
        "myDIV").style.columnRuleColor =
        "inherit";
}
```

## 输出示例

**点击前:**
![](img/37a08561e08742e3e3638610432b77c1.png)

**点击后:**
![](img/4188f4e93ef672a15789942da90d36ce.png)

## 浏览器支持

以下列出了 *HTML | DOM Style column rule color Property* 支持的浏览器:

*   谷歌 Chrome
*   边缘
*   旅行队
*   歌剧