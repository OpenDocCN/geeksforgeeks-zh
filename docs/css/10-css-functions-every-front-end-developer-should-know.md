# 每个前端开发者都应该知道的 10 个 CSS 功能

> 原文:[https://www . geesforgeks . org/10-CSS-functions-every-front-end-developer-应知/](https://www.geeksforgeeks.org/10-css-functions-every-front-end-developer-should-know/)

像所有其他编程语言一样， **CSS** 也有它们的功能。CSS 函数用作各种 CSS 属性的值。与其他编程语言不同，我们不能用 CSS 编写自己的函数。

让我们来看看您应该知道的一些重要的 CSS 函数–

**1。[网址()功能](https://www.geeksforgeeks.org/css-url-function/) :** 该功能用于设置背景图像、列表样式、列表样式图像、内容、光标、边框、边框图像、边框图像源、蒙版、蒙版图像。

```html
background: url("photo.jpg")
```

**2。[计算()函数](https://www.geeksforgeeks.org/css-calc-function/) :** 该函数用于执行计算。

```html
width: calc(100%-60px)
```

**3。 [var()函数](https://www.geeksforgeeks.org/css-var-function/) :** 该函数用于插入 CSS 变量的值。

```html
--white: #fff
h2 { color: var(--white); }
```

**4。 [rgb()](https://www.geeksforgeeks.org/css-rgb-function/) & [rgba()](https://www.geeksforgeeks.org/css-rgba-function/) 功能:**用来描述颜色的层次，这里‘r’代表红色，‘g’代表绿色，‘b’代表蓝色，‘a’用来指定一种颜色的不透明度。

```html
color: rgb(0, 0, 0)
color: rgba(0, 0, 0, 1)
```

**5。 [hsl()函数](https://www.geeksforgeeks.org/css-hsl-function/) :** 该函数用于使用色调、饱和度和明度来描述颜色的等级。

```html
color: hsl(0, 0, 0)
```

**6。[模糊()功能](https://www.geeksforgeeks.org/css-blur-function/) :** 用于应用模糊效果。

```html
.body{
    filter : blur(100px);
}
```

**7。[亮度()功能](https://www.geeksforgeeks.org/css-brightness-function/):帮助调节亮度。**

```html
.h2{
    filter: brightness(50%);
}
```

**8。[不透明度()功能](https://www.geeksforgeeks.org/css-opacity-function/) :** 帮助设置元素的不透明度。

```html
img{
    filter : opacity(50%);
}
```

**9。 [:not()功能](https://www.geeksforgeeks.org/css-notlast-childafter-selector/) :** 将样式应用于没有的 img 元素。无 p 级。

```html
img:not(.no-p){
    padding: 0;
}
```

**10。[:第 n 个子()](https://www.geeksforgeeks.org/css-nth-child-selector/) & [:第 n 个-最后一个子()](https://www.geeksforgeeks.org/css-nth-last-child-selector/)选择器:**选择一组元素中的一个或多个元素。

```html
li:nth-child(2), 
li:nth-last-child(2){
    color: yellow;
}
```