# CSS 文本转换属性

> 原文:[https://www.geeksforgeeks.org/css-text-transform-property/](https://www.geeksforgeeks.org/css-text-transform-property/)

**文本转换**属性用于控制文本的大小写。
**语法:**

```html
text-transform: none|capitalize|uppercase|lowercase|initial|inherit; 
```

**房产价值:**

*   **无:**有默认值。它没有大写。
    **语法:**

```html
text-transform: none;
```

*   **例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        CSS text-transform Property
    </title>
    <style>
        h1 {
            color: green;
        }

        p.gfg {
            text-transform: none;
        }
    </style>
</head>

<body>
    <center>
        <h1>GeeksForGeeks</h1>

        <h2>text-transform: none:</h2>
        <p class="gfg">GeeksforGeeks</p>

        <p class="gfg">
         It is a computer science portal for geeks.
        </p>

</body>

</html>
```

*   **输出:**

![](img/b6e64b43e756c3201838ea41af12c33a.png)

*   **大写:**用于将每个单词的第一个字符转换为大写。
    **语法:**

```html
text-transform:capitalize;
```

*   **例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        CSS text-transform Property
    </title>
    <style>
        h1 {
            color: green;
        }

        p.gfg {
            text-transform: capitalize;
        }
    </style>
</head>

<body>
    <center>
        <h1>GeeksForGeeks</h1>

        <h2>text-transform: capitalize:</h2>
        <p class="gfg">GeeksforGeeks</p>

        <p class="gfg">
         It is a computer science portal for geeks.
        </p>

</body>

</html>
```

*   **输出:**

![](img/6217f9f503279e1ca1bbf29c781ffb4f.png)

*   **大写:**用于将每个单词中的所有字符转换或变换为大写。
    **语法:**

```html
text-transform:uppercase;
```

*   **例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        CSS text-transform Property
    </title>
    <style>
        h1 {
            color: green;
        }

        p.gfg {
            text-transform: uppercase;
        }
    </style>
</head>

<body>
    <center>
        <h1>GeeksForGeeks</h1>

        <h2>text-transform: uppercase:</h2>
        <p class="gfg">GeeksforGeeks</p>

        <p class="gfg">
         It is a computer science portal for geeks.
        </p>

</body>

</html>
```

*   **输出:**

![](img/18221c382ff16859c4e3be36346aec1e.png)

*   **小写:**用于将每个单词中的所有字符转换或变换为 alowercase。
    **语法:**

```html
text-transform:lowercase;
```

*   **例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        CSS text-transform Property
    </title>
    <style>
        h1 {
            color: green;
        }

        p.gfg {
            text-transform: lowercase;
        }
    </style>
</head>

<body>
    <center>
        <h1>GeeksForGeeks</h1>

        <h2>text-transform: lowercase:</h2>
        <p class="gfg">GeeksforGeeks</p>

        <p class="gfg">
         It is a computer science portal for geeks.
        </p>

</body>

</html>
```

*   **输出:**

![](img/abf88f8d0c646ea324561afa045a6ad8.png)

*   **初始值:**将属性设置为默认值。
    **语法:**

```html
text-transform:initial;
```

*   **例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        CSS text-transform Property
    </title>
    <style>
        h1 {
            color: green;
        }

        p.gfg {
            text-transform: initial;
        }
    </style>
</head>

<body>
    <center>
        <h1>GeeksForGeeks</h1>

        <h2>text-transform: initial:</h2>
        <p class="gfg">GeeksforGeeks</p>

        <p class="gfg">
         It is a computer science portal for geeks.
        </p>

</body>

</html>
```

*   **输出:**

![](img/cd1737039e98381897e9d3794e6cfe78.png)

**支持的浏览器:**CSS 文本转换属性支持的浏览器如下:

*   谷歌 Chrome 1.0
*   Internet Explorer 4.0
*   Firefox 1.0
*   Opera 1.0
*   Safari 3.5