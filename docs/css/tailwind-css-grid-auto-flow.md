# 顺风 CSS 网格自动流动

> 原文:[https://www.geeksforgeeks.org/tailwind-css-grid-auto-flow/](https://www.geeksforgeeks.org/tailwind-css-grid-auto-flow/)

这个类在 tailwind CSS 中接受多个值，所有的属性都以类的形式被覆盖。它是 [CSS 网格自动流动属性](https://www.geeksforgeeks.org/css-grid-auto-flow-property/)的替代，用于指定自动放置的项目如何使用 Tailwind CSS 流入网格项目。

**电网自动流量:**

*   网格流行
*   网格流列
*   网格流行密集
*   网格流密集

**网格-流-行:**自动放置算法通过依次填充每行来放置项目，根据需要添加新行。

**语法:**

```html
<element class="grid-flow-row"> Contents... </element>
```

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html> 
<html>

<head> 
    <title>Tailwind grid-flow-row Class</title> 
    <link href=
"https://unpkg.com/tailwindcss@^1.0/dist/tailwind.min.css" 
          rel="stylesheet"> 
</head> 

<body class="text-center"> 
    <h1 class="text-green-600 text-5xl font-bold">
        GeeksforGeeks
    </h1> 

    <b>Tailwind CSS grid-flow-row Class</b> 

    <div class = "m-8 grid grid-flow-row gap-1">  
        <div class = "bg-green-300 rounded-lg">1</div>  
        <div class = "bg-green-300 rounded-lg">2</div>  
        <div class = "bg-green-300 rounded-lg">3</div>  
        <div class = "bg-green-300 rounded-lg">4</div>  
    </div>  
</body> 

</html>
```

**输出:**

![](img/d300321518b1bf9ec97e61408febe15f.png)

**网格-流-列:**自动放置算法通过依次填充每一列来放置项目，根据需要添加新列。

**语法:**

```html
<element class="grid-flow-col"> Contents... </element>
```

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html> 
<html>

<head> 
    <title>Tailwind grid-flow-col Class</title> 
    <link href=
"https://unpkg.com/tailwindcss@^1.0/dist/tailwind.min.css" 
          rel="stylesheet"> 
</head> 

<body class="text-center"> 
    <h1 class="text-green-600 text-5xl font-bold">
        GeeksforGeeks
    </h1> 

    <b>Tailwind CSS grid-flow-col Class</b> 

    <div class = "m-8 grid grid-flow-col gap-1">  
        <div class = "bg-green-300 rounded-lg">1</div>  
        <div class = "bg-green-300 rounded-lg">2</div>  
        <div class = "bg-green-300 rounded-lg">3</div>  
        <div class = "bg-green-300 rounded-lg">4</div>  
    </div>  
</body> 

</html>
```

**输出:**

![](img/60a10a386b2704180d7a3101e391ec79.png)

**网格-流-行-密集:**指定自动布局算法对列使用“密集”填充算法。

**语法:**

```html
<element class="grid-flow-row-dense"> Contents... </element>
```

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head> 
    <title>Tailwind grid-flow-row-dense Class</title> 
    <link href=
"https://unpkg.com/tailwindcss@^1.0/dist/tailwind.min.css" 
          rel="stylesheet"> 
</head> 

<body class="text-center"> 
    <h1 class="text-green-600 text-5xl font-bold">
        GeeksforGeeks
    </h1> 

    <b>Tailwind CSS grid-flow-row-dense Class</b> 

    <div class = "m-8 grid grid-flow-row-dense gap-1">  
        <div class = "bg-green-300 rounded-lg">1</div>  
        <div class = "bg-green-300 rounded-lg">2</div>  
        <div class = "bg-green-300 rounded-lg">3</div>  
        <div class = "bg-green-300 rounded-lg">4</div>  
    </div>  
</body> 

</html>
```

**输出:**

![](img/03427197c48a5e68f0890311d806e935.png)

**网格-流-列-密集:**指定自动布局算法对行使用“密集”填充算法。

**语法:**

```html
<element class="grid-flow-col-dense">..</element>
```

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html> 
<html>

<head> 
    <title>Tailwind grid-flow-col-dense Class</title> 
    <link href=
"https://unpkg.com/tailwindcss@^1.0/dist/tailwind.min.css" 
          rel="stylesheet"> 
</head> 

<body class="text-center"> 
    <h1 class="text-green-600 text-5xl font-bold">
        GeeksforGeeks
    </h1> 

    <b>Tailwind CSS grid-flow-col-dense Class</b> 

    <div class = "m-8 grid grid-flow-col-dense gap-1">  
        <div class = "bg-green-300 rounded-lg">1</div>  
        <div class = "bg-green-300 rounded-lg">2</div>  
        <div class = "bg-green-300 rounded-lg">3</div>  
        <div class = "bg-green-300 rounded-lg">4</div>  
    </div>  
</body> 

</html>
```

**输出:**

![](img/e6b62df67d23247b3bf79e5112eb5c27.png)