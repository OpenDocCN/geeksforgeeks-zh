# CSS 属性选择器

> 原文: [https://www.geeksforgeeks.org/css-attribute-selector/](https://www.geeksforgeeks.org/css-attribute-selector/)

CSS 属性选择器用于选择具有特定属性或属性值的元素。根据某些特定属性对 HTML 元素进行分组是一种很好的样式化方法，属性选择器将选择那些具有相似属性的元素。

属性选择器有几种类型，下面讨论：

## `[attribute]` 选择器

这种类型的属性选择器用于选择所有具有指定属性的元素，并将 CSS 属性应用于该属性。例如，选择器 `[class]` 将选择所有具有 `style` 属性的元素。

**示例:**

```html
<!DOCTYPE html>
<html>
    <head>
        <title>Attributes selector</title>
        <style>
            [class] {
                text-align:center;
                Color:green;
            }
            .gfg {
                font-size:40px;
                font-weight:bold;
                margin-bottom:-20px;
            }
        </style>
    </head>
    <body>
        <div class = "gfg">GeeksforGeeks</div>
        <p class = "geeks">A computer science portal for geeks</p>
    </body>
</html>
```

**输出:**
![attribute selector](img/50dc47b538eab3b07ed7bffb9d17c462.png)

这个选择器用于限制某些特定的元素，那么它需要在属性选择器之前指定那个元素。

**例:**

```html
<!DOCTYPE html>
<html>
    <head>
        <title>Attribute selector</title>
        <style>
            div[style] {
                text-align:center;
                color:green;
                font-size:40px;
                font-weight:bold;
                margin-bottom:-20px;
            }
            p {
                text-align:center;
                font-size:17px;
            }
        </style>
    </head>
    <body>
        <div style = "color:green">GeeksforGeeks</div>
        <p>A computer science portal for geeks</p>
    </body>
</html>
```

**输出:**
![attribute selector](img/5edc5593de9dac82f07a2e4f68d401cb.png)

可以使用逗号运算符选择多个元素。

```css
h2, p[style] {
    background-color: #00b93e;
}
```

## `[attribute="value"]` 选择器

此选择器用于选择所有属性值与指定值完全相同的元素。

**示例:**

```html
<!DOCTYPE html>
<html>
    <head>
        <title>Attribute selector</title>
        <style>
            [title = "gfg"] {
                color:green;
                font-size:40px;
                font-weight:bold;
                text-align:center;
            }
            [title = "geeks"] {
                font-size:17px;
                text-align:center;
                margin-top:0px;
            }
        </style>
    </head>
    <body>
        <div title = "gfg">GeeksforGeeks</div>
        <p title = "geeks">A computer science portal for geeks</p>
    </body>
</html>
```

**输出:**
![attribute selector](img/5edc5593de9dac82f07a2e4f68d401cb.png)

## `[attribute~="value"]` 选择器

此选择器用于选择所有属性值是一个以空格分隔的列表，且其中一项与指定值完全相等的元素。

**示例:**

```html
<!DOCTYPE html>
<html>
    <head>
        <title>Attribute selector</title>
        <style>
            [class~="gfg"] {
                color:green;
                font-size:40px;
                font-weight:bold;
                text-align:center;
            }
            [class~="geeks"] {
                font-size:17px;
                text-align:center;
                margin-top:0px;
            }
        </style>
    </head>
    <body>
        <div class = "gfg">GeeksforGeeks</div>
        <div Class = "geeks">A computer science portal for geeks
        </div>
        <div class = "geeks ide">GeeksforGeeks is coding platform
        </div>
    </body>
</html>
```

**输出:**
![attribute selector](img/925f1209f4b4f4a363e3369b480f40a2.png)

## `[attribute|="value"]` 选择器

此选择器用于选择所有属性值是一个以连字符分隔的列表，且以指定值开头的元素。该值必须是一个完整的单词，可以单独存在，也可以后跟一个连字符。

**示例:**

```html
<!DOCTYPE html>
<html>
    <head>
        <title>Attribute selector</title>
        <style>
            [class|="gfg"] {
                color:green;
                font-size:40px;
                font-weight:bold;
                text-align:center;
            }
            [class|="geeks"] {
                font-size:17px;
                text-align:center;
                margin-top:0px;
            }
        </style>
    </head>
    <body>
        <div class = "gfg">GeeksforGeeks</div>
        <div Class = "geeks-ide">A computer science portal for geeks
        </div>
        <div class = "geeks-ide1">GeeksforGeeks is coding platform
        </div>
    </body>
</html>
```

**输出:**
![attribute selector](img/925f1209f4b4f4a363e3369b480f40a2.png)

## `[attribute^="value"]` 选择器

此选择器用于选择所有属性值以指定值开头的元素。该值不需要是一个完整的单词。

**示例:**

```html
<!DOCTYPE html>
<html>
    <head>
        <title>Attribute selector</title>
        <style>
            [class^="gfg"] {
                color:green;
                font-size:40px;
                font-weight:bold;
                text-align:center;
            }
            [class^="geeks"] {
                font-size:17px;
                text-align:center;
                margin-top:0px;
            }
        </style>
    </head>
    <body>
        <div class = "gfg">GeeksforGeeks</div>
        <div Class = "geeks">A computer science portal for geeks
        </div>
        <div class = "geekside">GeeksforGeeks is coding platform
        </div>
    </body>
</html>
```

**输出:**
![attribute selector](img/925f1209f4b4f4a363e3369b480f40a2.png)

## `[attribute$="value"]` 选择器

此选择器用于选择所有属性值以指定值结尾的元素。该值不需要是一个完整的单词。

**示例:**

# 属性选择器示例

```html
<!DOCTYPE html>
<html>
    <head>
        <title>Attribute selector</title>
        <style>
            [class$="gfg"] {
                color:green;
                font-size:40px;
                font-weight:bold;
                text-align:center;
            }
            [class$="geeks"] {
                font-size:17px;
                text-align:center;
                margin-top:0px;
            }
        </style>
    </head>
    <body>
        <div class = "gfg">GeeksforGeeks</div>
        <div Class = "geeksforgeeks">A computer science portal for geeks
        </div>
        <div class = "geeks">GeeksforGeeks is coding platform
        </div>
    </body>
</html>
```

**输出:**
![attribute selector](img/925f1209f4b4f4a363e3369b480f40a2.png)

## `[attribute*="value"]` 选择器

此选择器选取所有属性值中任意位置包含指定值的元素。该值不必是一个完整的单词。

**示例:**

```html
<!DOCTYPE html>
<html>
    <head>
        <title>Attribute selector</title>
        <style>
            [class*="gfg"] {
                color:green;
                font-size:40px;
                font-weight:bold;
                text-align:center;
            }
            [class*="for"] {
                font-size:17px;
                text-align:center;
                margin-top:0px;
            }
        </style>
    </head>
    <body>
        <div class = "gfg">GeeksforGeeks</div>
        <div Class = "geeksforgeeks">A computer science portal for geeks
        </div>
        <div class = "geeks for">GeeksforGeeks is coding platform
        </div>
    </body>
</html>
```

**输出:**
![attribute selector](img/925f1209f4b4f4a363e3369b480f40a2.png)