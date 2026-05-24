# ReactJS |计算器应用程序(样式)

> 原文:[https://www . geeksforgeeks . org/reactjs-calculator-app-styling/](https://www.geeksforgeeks.org/reactjs-calculator-app-styling/)

在我们之前的文章中，我们在计算器应用程序中添加了功能，并使用 React 成功创建了一个功能齐全的计算器应用程序。尽管功能齐全，但看起来并不好。这是因为代码中缺少 CSS。让我们在我们的应用程序中添加 CSS，让它看起来更有吸引力和美观。
还记得我们最初创建了一个名为“index.css”的文件吗？我们将把所有的 CSS 代码写在这个文件中。但是在此之前，让我们将这个文件包含在我们的 **index.js** 文件中，这样我们就可以在浏览器中立即看到我们在 CSS 中所做的更改的效果。在我们的 index.js 文件的顶部写下下面一行代码:

```jsx
import './index.css';
```

现在，让我们开始写我们的 CSS。我们首先要做的是为所有元素设置默认值。在 index.css 文件的顶部写下下面的代码:

## 半铸钢ˌ钢性铸铁(Cast Semi-Steel)

```jsx
*{
    margin:0px;
    padding:0px;
    border-radius: 0px;
    box-sizing: border-box;
    font-size: 110%;
}

#root{
    text-align:center;
}
```

接下来我们要做的是给 CalculatorTitle 组件添加样式。我们把这个元素的类名称为“计算器标题”。因此，我们将使用这个类添加样式。我们将标题与中心对齐，添加填充、边距、宽度、背景颜色、文本颜色等。下面的代码用于设置 CalculatorTitle 组件的样式:

## 半铸钢ˌ钢性铸铁(Cast Semi-Steel)

```jsx
.calculator-title{
    font-size:30px;
    background: #fff;
    width: 400px;
    padding: 10px 10px;
    margin: 0 auto;
    margin-top: 20px;
    margin-bottom: 20px;
    border-radius: 2px;
    border: 2px solid black;
    color: #4CAF50;
}
```