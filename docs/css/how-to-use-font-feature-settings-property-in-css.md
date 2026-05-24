# 如何在 CSS 中使用字体-特征-设置属性？

> 原文:[https://www . geeksforgeeks . org/如何使用-字体-功能-设置-属性-in-css/](https://www.geeksforgeeks.org/how-to-use-font-feature-settings-property-in-css/)

如果你想控制开放字体的高级排版功能，那么**字体-功能-设置**属性对开发者非常有用。

通过使用这个属性，我们可以控制高级排字设置，如 swashes、小大写和连字。为了激活它们，您必须在引号中声明值，后跟 1 或 on(如果您想启用)。如果您想禁用它，您可以使用 0 或关闭。

**语法:**

```html
font-feature-settings: values;
```

**属性值:**该属性接受下述属性值。

*   **值:**该属性是指像*、【smcp】、【smcp】on、【swsh】on、*等 OpenType 特征标签定义的值。它的全局值为:*“继承”、“初始”*、*“取消设置”。*

**注意:***字体-特征-设置*默认值正常。

**示例 1:** 以下是使用值“hlig”说明*字体-特征-设置*属性的使用的示例。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>
  <head>
    <style type="text/css">
      p {
        color: green;
        padding: 7px;
        font-weight: bold;
        font-feature-settings: "hlig" 4;
      }
    </style>
  </head>

  <body>

<p>GeeksforGeeks!</p>

  </body>
</html>
```

**输出:**

![](img/b5edd6024f8a0d2fc1e843d8cc0fc848.png)

hlig 的字体功能

**示例 2:** 以下是使用值“smcp”和“swsh”说明*字体特征设置*属性使用的示例。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>
  <head>
    <style type="text/css">
      p {
        color: green;
        padding: 8px;
        font-weight: bold;
        font-style: italic;
        font-feature-settings: "smcp", "swsh" 5;
      }
    </style>
  </head>

  <body>

<p>It is a Computer Science portal</p>

  </body>
</html>
```

**输出:**

![](img/78a25a313edbd7bef32249f493e6e6c4.png)