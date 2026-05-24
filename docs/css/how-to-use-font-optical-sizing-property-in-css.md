# 如何在 CSS 中使用字体光学大小属性？

> 原文:[https://www . geesforgeks . org/如何使用-字体-光学-尺寸-属性-in-css/](https://www.geeksforgeeks.org/how-to-use-font-optical-sizing-property-in-css/)

无论我们现在制作什么样的网络应用程序或网站，我们都会确保它兼容所有的屏幕尺寸。所以 CSS 附带了**字体光学尺寸**属性，该属性设置正在渲染的文本是否针对不同的屏幕尺寸进行了优化。它允许浏览器调整字体字形的轮廓，使它们更适合不同的大小。

如果字体支持**字体光学尺寸**属性，那么使用这种方法将是光学尺寸最有效的方法。如果我们谈论支持这个属性的字体，那么我们可以说所有的可变字体都支持这个属性。对于那些具有光学尺寸变化轴的字体，默认情况下会启用光学尺寸。

**语法:**

**字体光学尺寸**属性的语法如下。

```html
font-optical-sizing: value;
```

**属性值:**该属性接受下述属性值。

*   **关键字 _ 值:**该属性的值是指*【自动】【无】*等定义的值。
*   **global_values:** 该属性的值是指*定义的“继承”、“初始”、“未设置”的值。*

**示例 1:** 以下是使用属性值“*自动*说明*字体光学尺寸*属性使用的示例。网页会自行调整，以保持字形或字符的形状，从而获得最佳观看效果。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
  <style type="text/css">
    p { 
      color: green;
      padding: 5px;
      font-weight: bold;
      font-optical-sizing: auto;
     }
  </style>
</head>
<body>
  <p>Hello GeeksforGeeks!</p>
</body>

</html>
```

**输出:**

![](img/7e0faaa2287c3691cb389e3c37d8864d.png)

自动设置

**示例 2:** 以下是使用值“**初始**说明*字体光学尺寸*属性的示例。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>
<head>
  <style type="text/css">
    p { 
      color: green;
      padding: 6px;
      font-weight: bold;
      font-style: italic;
      font-optical-sizing: initial;
     }
    </style>
</head>

<body>
  <p>Welcome to this Computer Science portal</p>
</body>  
</html>
```

**输出:**

![](img/92e5fe68492dfe595948cb276fcda221.png)

初调