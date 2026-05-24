# 如何应用 CSS 填充速记属性？

> 原文:[https://www . geesforgeks . org/how-apply-CSS-padding-速记-property/](https://www.geeksforgeeks.org/how-to-apply-css-padding-shorthand-property/)

**填充**是元素与其边框之间的空间。padding 的速记属性设置元素所有四边的填充区域。填充值可以是 px、em、rem 或%。如果我们想在特定的一侧应用填充，我们可以使用以下属性:

*   **[填充-左侧](https://www.geeksforgeeks.org/css-padding-left-property/) :** 在元素左侧设置填充。
*   **[填充-右侧](https://www.geeksforgeeks.org/css-padding-right-property/) :** 在元素右侧设置填充。
*   **[填充-顶部](https://www.geeksforgeeks.org/css-padding-top-property/) :** 在元素的顶部设置填充。
*   **[填充-底部](https://www.geeksforgeeks.org/css-padding-bottom-property/) :** 在元素的底部设置填充。

**语法:**

```html
padding: value;
```

不同的垂直和水平填充:

```html
padding: value1 value2;
```

1.  **值 1:** 设置元素顶部和底部的填充值。
2.  **值 2:** 设置元素右侧和左侧的填充值。

不同的顶部、水平和底部填充:

```html
padding: value1 value2 value3;
```

1.  **值 1:** 设置元素顶部的填充。
2.  **值 2:** 在元素的右侧和左侧设置填充。
3.  **值 3:** 设置元素底部的填充。

四面都有不同的衬垫:

```html
padding: value1 value2 value3 value4;
```

1.  **值 1:** 设置元素顶部的填充。
2.  **值 2:** 设置元素右侧的填充。
3.  **值 3:** 设置元素底部的填充。
4.  **值 4:** 设置元素左侧的填充。

**示例 1:** 仅具有 1 个值的填充

## 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" 
          content="width=device-width, initial-scale=1.0">
    <style>
        h1{
            width: fit-content;
            border: 4px solid #308D46;
            color: #308D46;
            padding: 20px;
        }
    </style>

</head>
<body>
   <h1> GeeksforGeeks</h1>
</body>
</html>
```

**输出:**

![](img/eb2668f1788332333d86101cc775c31c.png)

**示例 2:** 填充两个值

## 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" 
          content="width=device-width, initial-scale=1.0">
    <style>
        h1{
            width: fit-content;
            border: 4px solid #308D46;
            color: #308D46;
            padding: 5px 40px;
        }
    </style>

</head>
<body>
   <h1> GeeksforGeeks</h1>
</body>
</html>
```

**输出:**

![](img/a9dd0d29a1fdeeac9b47b1beeeaf6a3c.png)

**示例 3:** 填充三个值

## 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" 
          content="width=device-width, initial-scale=1.0">
    <style>
        h1{
            width: fit-content;
            border: 4px solid #308D46;
            color: #308D46;
            padding: 5px 40px 30px;
        }
    </style>
</head>
<body>
   <h1> GeeksforGeeks</h1>
</body>
</html>
```

**输出:**

![](img/24ea0f5c4c79d5b0569a0bae51e36e27.png)

**例 4:** 四值填充

## 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport"
          content="width=device-width, initial-scale=1.0">
    <style>
        h1{
            width: fit-content;
            border: 4px solid #308D46;
            color: #308D46;
            padding: 15px 40px 45px 5px;
        }
    </style>

</head>
<body>
   <h1> GeeksforGeeks</h1>
</body>
</html>
```

**输出:**

![](img/aa69b280f18bd97671a8263e2a04f9c9.png)