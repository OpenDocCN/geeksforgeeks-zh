# CSS `line-height` 属性

> 原文：[https://www.geeksforgeeks.org/css-line-height-property/](https://www.geeksforgeeks.org/css-line-height-property/)

CSS 中的 `line-height` 属性用于设置用于行的空间量，例如在文本中。不允许负值。

## 语法

```css
line-height: normal|number|length|percentage|initial|inherit;
```

## 属性值

### `normal`
此模式代表正常的行高。这是默认值。

```css
line-height: normal;
```

**示例：**

```html
<!DOCTYPE html>
<html>
    <head>
        <title>CSS line-height Property</title>
        <style>
            .geek {
              line-height: normal;
              background: green;
              color: white;
            }
        </style>
    </head>
    <body style = "text-align:center;">
        <h1 style = "color:green;">
            GeeksforGeeks
        </h1>
        <h2>
            CSS line-height Property
        </h2>
        <div class="geek">
            A computer science portal for geeks.<br>
            This div has line-height: normal;
        </div>
    </body>
</html>
```

**输出：**
![lineheight](img/c4a15273870318fd2aa29459b828a438.png)

### `number`
此值是一个无单位的数字，乘以当前的 `font-size` 来设置行高。在大多数情况下，这是设置 `line-height` 的首选方法，可以避免因继承而导致的意外结果。

```css
line-height: 2.5;
```

**示例：**

```html
<!DOCTYPE html>
<html>
    <head>
        <title>CSS line-height Property</title>
        <style>
            .geek {
              line-height: 2.5;
              background: green;
              color: white;
            }
        </style>
    </head>
    <body style = "text-align:center;">
        <h1 style = "color:green;">
            GeeksforGeeks
        </h1>
        <h2>
            CSS line-height Property
        </h2>
        <div class="geek">
            A computer science portal for geeks.<br>
            This div has line-height: 2.5;
        </div>
    </body>
</html>
```

**输出：**
![lineheight](img/564c10cc326060e445caf92fa7cdce35.png)

### `length`
在此模式下，指定了一个固定的行高。

```css
line-height: 2em;
```

**示例：**

```html
<!DOCTYPE html>
<html>
    <head>
        <title>CSS line-height Property</title>
        <style>
            .geek {
              line-height: 2em;
              background: green;
              color: white;
            }
        </style>
    </head>
    <body style = "text-align:center;">
        <h1 style = "color:green;">
            GeeksforGeeks
        </h1>
        <h2>
            CSS line-height Property
        </h2>
        <div class="geek">
            A computer science portal for geeks.<br>
            This div has line-height: 2em;
        </div>
    </body>
</html>
```

**输出：**
![lineheight](img/82cbf6df1c68b420e214e367cfbcd12a.png)

### `percentage`
此模式用于以当前字体大小的百分比来设置行高。

```css
line-height: 150%;
```

**示例：**

```html
<!DOCTYPE html>
<html>
    <head>
        <title>CSS line-height Property</title>
        <style>
            .geek {
              line-height: 150%;
              background: green;
              color: white;
            }
        </style>
    </head>
    <body style = "text-align:center;">
        <h1 style = "color:green;">
            GeeksforGeeks
        </h1>
        <h2>
            CSS line-height Property
        </h2>
        <div class="geek">
            A computer science portal for geeks.<br>
            This div has line-height: 150%;
        </div>
    </body>
</html>
```

**输出：**
![lineheight](img/0dc295dcf88694a2cae5de1a527495cc.png)

### `initial`
该模式用于将该属性设置为默认值。

```css
line-height: initial;
```

## 支持的浏览器
`line-height` 属性支持的浏览器如下：

*   Google Chrome 1.0
*   Internet Explorer 4.0
*   Firefox 1.0
*   Opera 7.0
*   Apple Safari 1.0