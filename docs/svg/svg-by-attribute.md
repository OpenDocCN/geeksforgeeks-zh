# 属性支持向量机

> 原文:[https://www.geeksforgeeks.org/svg-by-attribute/](https://www.geeksforgeeks.org/svg-by-attribute/)

**by** 属性指定动画期间将被修改的属性的相对偏移值。

**语法:**

```html
by="numbers"
```

**属性值:**

*   **整数:**我们要设置 by 属性的整数。

我们将使用 by 属性来调整形状的大小。

**例 1:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<body>
    <svg viewBox="0 0 100 100" 
        xmlns="http://www.w3.org/2000/svg">

        <rect x="5" y="5" width="20" height="20">
            <animate attributeName="width" 
            fill="freeze" by="20" dur="4s" />
        </rect>
    </svg>
</body>

</html>
```

**输出:**

![](img/cd55bab62abad9939c55c4da9996c6d9.png)

**例 2:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<body>
    <svg viewBox="0 0 100 100" 
        xmlns="http://www.w3.org/2000/svg">

        <rect x="5" y="5" width="20" height="10">
            <animate attributeName="height" 
                fill="freeze" by="10" dur="4s" />
        </rect>
    </svg>
</body>

</html>
```

**输出:**

![](img/3b3802fab9f7b428b4c68a0eeb71eeea.png)