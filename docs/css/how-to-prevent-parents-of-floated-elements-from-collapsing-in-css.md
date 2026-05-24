# 如何防止 CSS 中浮动元素的父元素崩溃？

> 原文:[https://www . geeksforgeeks . org/如何防止浮动元素的父元素在 css 中崩溃/](https://www.geeksforgeeks.org/how-to-prevent-parents-of-floated-elements-from-collapsing-in-css/)

众所周知，像 *div* 、*段落*、*文本*等 HTML 元素。成长以适应孩子的内容。但是如果这些元素的子元素是向右或向左浮动的，那么父母可能会崩溃。也就是说，他们会失去他们的实际行为。

让我们用一个**例子**来理解这一点:考虑下面的代码。在下面的程序中，一个绿色背景的父 div 还有 6 个子 div 元素。父母和孩子都不在这里。让我们编译并查看代码的输出。

## 超文本标记语言

```html
<!DOCTYPE>
<html>
<head>
    <title>Floats and collapsing parents</title>
    <style>
        div{
             padding: 5px;   
        }
    </style>
</head>
<body>
    <!-- Parent Div -->
    <div style="background-color: green;">

        <!-- Children div's begins -->
        <div>HTML5</div> 
        <div>CSS3</div>
        <div>JavaScript</div>
        <div>Python</div>
        <div>MySQL</div>
        <div>MongoDB</div>
        <!-- Children div's ends -->

    </div>
</body>
</html>                    
```

**Output**:
![](img/71f43e5cbf86fe249d50f1b5b9d40fa2.png)

现在让我们将上面代码中的所有**子 div 向左浮动**，并查看输出中的差异:

## 超文本标记语言

```html
<!DOCTYPE>
<html>
<head>
    <title>Floats and collapsing parents</title>
    <style>
        div{
             padding: 5px;   
        }
    </style>
</head>
<body>
    <!-- Parent Div -->
    <div style="background-color: green;">

        <!-- Children div's begins, floated to left -->
        <div style="float: left;">HTML5</div> 
        <div style="float: left;">CSS3</div>
        <div style="float: left;">JavaScript</div>
        <div style="float: left;">Python</div>
        <div style="float: left;">MySQL</div>
        <div style="float: left;">MongoDB</div>
        <!-- Children div's ends -->

    </div>
</body>
</html>                    
```