# 如何在 CSS 中使用字体-变体-设置属性？

> 原文:[https://www . geesforgeks . org/如何使用-字体-变体-设置-属性-in-css/](https://www.geeksforgeeks.org/how-to-use-font-variant-settings-property-in-css/)

**字体变体设置**属性允许用户对具有可变特征的字体进行良好的低级控制。用户可以指定要改变其值的字符的字体字母轴名称。

有两种形式来指定这个属性，一种是普通的，第二种是字符串数字。当应用*正常*属性时，文本将按照默认设置进行布局。此属性是一种低级机制，旨在让用户可以设置可变字体功能。

**语法:***字体变化设置*属性的语法如下所示。

```html
font-variant-settings: normal | small-caps | initial | inherit;
```

**属性值:**

*   **默认值:**要使用默认设置，使用的值是*“正常”。*
*   **全局 _ 值:**全局值定义为*“继承”、“初始”、“恢复”和“取消设置”。*

**示例 1:** 以下是*字体-变体-设置*使用值“正常”的示例。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <style type="text/css">
        p.normal {
            color: green;
            padding: 7px;
            font-weight: bold;
            font-variant: normal;
        }
    </style>
</head>

<body>
    <p class="normal">
        Hello, this is GeeksforGeeks!!
    </p>
</body>

</html>
```

**输出:**

![](img/b5cf1c3b280d62fe36296d4c7f4de9db.png)

**示例 2:** 以下是*字体变体设置*使用值“小写”的示例。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <style type="text/css">
        p.small {
            color: green;
            padding: 12px;
            font-weight: bold;
            font-variant: small-caps;
        }
    </style>
</head>

<body>
    <p class="small">
        Hello, this is GeeksforGeeks!!
    </p>
</body>

</html>
```

**输出:**

![](img/59a1df9f4edc1ca30c766e617b10a2f5.png)

小盘股

**支持的浏览器:**

*   铬
*   火狐浏览器
*   歌剧
*   旅行队
*   边缘
*   微软公司出品的 web 浏览器