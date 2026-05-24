# 泰风 CSS 平移

> 哎哎哎:# t0]https://www . geeksforgeeks . org/taiwind-CSS-translate/

这个类在[顺风 CSS](https://www.geeksforgeeks.org/css-tailwind-introduction/) 中接受很多值，其中所有的属性都以类的形式被覆盖。这个类用于转换元素。在 CSS 中，我们通过使用 [CSS translate()函数](https://www.geeksforgeeks.org/css-translate-function/)做到了这一点。

**平移类:**

*   **translate-x-{amount}:** 此类保存 x 轴对应的平移长度。
*   **-translate-x-{amount}:** 此参数保存反向 x 轴对应的平移长度。
*   **平移-y-{amount}:** 此参数保存 y 轴对应的平移长度。
*   **-translate-y-{amount}:** 此参数保存反向 y 轴对应的平移长度。

**注意:**金额完全取决于你的选择，你可以设置为百分比满，也可以直接放 rem 值。

**语法:**

```html
<element class="translate-{axis}-{amount}">...</element>
```

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html> 
<html> 
<head> 
    <link href= 
"https://unpkg.com/tailwindcss@^1.0/dist/tailwind.min.css"
    rel="stylesheet"> 
</head> 

<body class="text-center"> 
    <h1 class="text-green-600 text-5xl font-bold"> 
       GeeksforGeeks 
    </h1> 
    <b>Tailwind CSS Translate Class</b> 
    <div class="bg-green-300 
                mx-16
                p-4
                justify-between 
                grid grid-flow-col"> 
    <div class="bg-no-repeat
                w-16 h-16 transform translate-x-16" 
        style= 
        "background-image:url( 
https://media.geeksforgeeks.org/wp-content/uploads/20210222211217/Screenshot20210222211207.png)"> 
    </div> 
    <div class="bg-no-repeat 
                w-16 h-16 transform translate-y-16" 
        style= 
        "background-image:url( 
https://media.geeksforgeeks.org/wp-content/uploads/20210222211217/Screenshot20210222211207.png)"> 
    </div>
    <div class="bg-no-repeat 
                w-16 h-16 transform -translate-x-16" 
        style="background-image:url( 
https://media.geeksforgeeks.org/wp-content/uploads/20210222211217/Screenshot20210222211207.png)"> 
    </div> 
    <div class="bg-no-repeat 
                w-16 h-16 transform -translate-y-16" 
        style="background-image:url( 
https://media.geeksforgeeks.org/wp-content/uploads/20210222211217/Screenshot20210222211207.png)"> 
    </div>
    </div> 
</body> 
</html> 
```

**输出:**

![](img/3f7db40901fd25253f4ffdc21ffe8e4e.png)

顺风 CSS 翻译类