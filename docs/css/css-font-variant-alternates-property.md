# CSS 字体-变体-替换属性

> 原文:[https://www . geesforgeks . org/CSS-font-variant-alternates-property/](https://www.geeksforgeeks.org/css-font-variant-alternates-property/)

**字体变体替换**属性是 CSS3 属性之一，通常用于启用各种字体相关功能，以改善页面上文本的外观。**字体变体替换**属性用于专门选择替换字形。

对于任何给定的字符，除了该字符的默认字形之外，字体还可以提供各种替代字形。通过**字体变体替换**属性，您可以选择在给定情况下您需要的特定字形。

**语法:**

```html
font-variant-alternates: normal | historical-forms | stylistic() |
                         styleset() | character-variant() |
                         swash() | ornaments() | annotation();

```

**房产价值:**

*   **关键字值:**它将关键字值作为“正常”和“历史形式”。
*   **功能记数值:**取功能记数值为“花体”、“装饰物”、“注释”、“样式集”、“文体”。
*   **全局值:**取全局值为“初始”、“继承”、“取消设置”。

**例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <style>
        @font-feature-values "Leitura Display Swashes" {
            @swash {
                fancy: 1;
            }
        }

        p {
            font-size: 5rem;
        }

        .variantAlternates {
            font-family: Leitura Display Swashes;
            font-variant-alternates: swash(fancy);
            color: green;
        }
    </style>
</head>

<body>
    <p class="variantAlternates">GeeksforGeeks</p>

</body>

</html>
```

**输出:**

![](img/7f04ff8986c792059f34d679baf4a008.png)

上述代码的输出。

**支持的浏览器:**只有火狐浏览器支持该属性。