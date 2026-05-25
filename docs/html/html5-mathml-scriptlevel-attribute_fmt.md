
# HTML5 MathML 脚本级属性

> 原文: [https://www.geeksforgeeks.org/html5-mathml-script-level-attribute/](https://www.geeksforgeeks.org/html5-mathml-script-level-attribute/)

该属性保存控制字体大小的值。它像优先级属性一样工作，这意味着优先级值越高，性能越低。这意味着脚本级别越高，字体越小。该属性仅被 `<mstyle>` 标签接受。

## 语法:

```html
<element scriptlevel="number">
```

## 属性值:

*   **编号:** 该值用于定义字体大小，类似于优先级属性，表示优先级值越高，性能越低。

## 示例:

## 超文本标记语言

```html
<!DOCTYPE html> 
<html>

<head> 
    <title>HTML5 MathML scriptlevel Attribute</title> 
</head>

<body> 
    <center> 
        <h1 style="color:green"> 
            GeeksforGeeks 
        </h1>

<h3>HTML5 MathML scriptlevel Attribute</h3>

<math> 
            <mstyle displaystyle="true"
                    mathcolor="purple"
                    scriptlevel="2"> 
                <mrow> 
                    <msubsup> 
                        <mo>∑</mo> 
                        <mn> i=1 </mn> 
                        <mn> n </mn> 
                    </msubsup> 
                    <mo>+</mo> 
                    <msub> 
                        <mi>x</mi> 
                        <mn>i</mn> 
                    </msub> 
                    <mo>=</mo> 
                    <mn>?</mn> 
                </mrow> 
            </mstyle> 
        </math> 
    </center> 
</body>

</html> 
```

## 输出:

![输出示例](img/7a3c1430513ce3870d404522a7499e28.png)

## 支持的浏览器:

*   火狐浏览器
