# CSS `border-right-width` 属性

> 原文：[https://www.geeksforgeeks.org/css-border-right-width-property/](https://www.geeksforgeeks.org/css-border-right-width-property/)

CSS 中的 `border-right-width` 属性用于设置元素右边框的宽度。必须在 `border-right-width` 属性之前声明 `border-style` 或 `border-right-style` 属性。

**默认值：**

*   `medium`

**语法：**

```html
border-right-width: medium|thin|thick|length|initial|inherit;
```

## 属性值

### `medium`
为默认值。它用于指定中等大小的右边框。

*   **语法：**

```html
border-right-width: medium;
```

*   **示例：**

```html
<!DOCTYPE html>
<html>
    <head>
        <title>
            CSS | border-right-width Property
        </title>
        <style>
            h3 {
                border: solid green;
                border-right-width: medium;
                width: 50%;
            }
            p {
                border-style:dotted;
                border-right-width:medium;
                width:70%;
            }
        </style>
    </head>

    <body>
        <center>
            <h1 style = "color:green">
             GeeksForGeeks
            </h1>
            <h2>border-right-width:initial;</h2>

            <!-- border-right-width property
                                   used here -->
            <h3>GeeksForGeeks</h3>

            <!-- border-right-width property
                                   used here -->

            <p>
             It is a computer science portal for geeks.
            </p>

        </center>
    </body>
</html>
```

*   **输出：**

![](img/2f3a70cd81386cbaf4a690ab3c77d937.png)

### `thin`
此属性用于将右边框宽度设置为薄。

*   **语法：**

```html
border-right-width: thin;
```

*   **示例：**

```html
<!DOCTYPE html>
<html>
    <head>
        <title>
            CSS | border-right-width Property
        </title>
        <style>
            h3 {
                border: solid green;
                border-right-width: thin;
                width: 50%;
            }
            p {
                border-style:dotted;
                border-right-width:thin;
                width:70%;
            }
        </style>
    </head>

    <body>
        <center>
            <h1 style = "color:green">
             GeeksForGeeks
            </h1>
            <h2>border-right-width:initial;</h2>

            <!-- border-right-width property
                                   used here -->
            <h3>GeeksForGeeks</h3>

            <!-- border-right-width property
                                   used here -->

            <p>
             It is a computer science portal for geeks.
            </p>

        </center>
    </body>
</html>
```

*   **输出：**

![](img/b55569a4297deee007ea9ad5e5cf1d00.png)

### `thick`
该属性用于指定元素的粗右边框。

*   **语法：**

```html
border-right-width: thick;
```

*   **示例：**

```html
<!DOCTYPE html>
<html>
    <head>
        <title>
            CSS | border-right-width Property
        </title>
        <style>
            h3 {
                border: solid green;
                border-right-width: thick;
                width: 50%;
            }
            p {
                border-style:dotted;
                border-right-width:thick;
                width:70%;
            }
        </style>
    </head>

    <body>
        <center>
            <h1 style = "color:green">
             GeeksForGeeks
            </h1>
            <h2>border-right-width:initial;</h2>

            <!-- border-right-width property
                                   used here -->
            <h3>GeeksForGeeks</h3>

            <!-- border-right-width property
                                   used here -->

            <p>
             It is a computer science portal for geeks.
            </p>

        </center>
    </body>
</html>
```

*   **输出：**

![](img/72ba9e92a0dae8ec2215cf8ccd3887bc.png)

### `length`
该属性用于设置右边框的厚度。

*   **语法：**

```html
border-right-width: length;
```

*   **示例：**

```html
<!DOCTYPE html>
<html>
    <head>
        <title>
            CSS | border-right-width Property
        </title>
        <style>
            h3 {
                border: solid green;
                border-right-width: 10px;
                width: 50%;
            }
            p {
                border-style:dotted;
                border-right-width:5px;
                width:70%;
            }
        </style>
    </head>

    <body>
        <center>
            <h1 style = "color:green">
             GeeksForGeeks
            </h1>
            <h2>border-right-width:initial;</h2>

            <!-- border-right-width property
                                   used here -->
            <h3>GeeksForGeeks</h3>

            <!-- border-right-width property
                                   used here -->

            <p>
             It is a computer science portal for geeks.
            </p>

        </center>
    </body>
</html>
```

*   **输出：**

![](img/7768eb43b955276f1a39d667862cbbb7.png)

### `initial`
用于将 `border-right-width` 属性设置为默认值。

*   **语法：**

```html
border-right-width: initial;
```

*   **示例：**

```html
<!DOCTYPE html>
<html>
    <head>
        <title>
            CSS | border-right-width Property
        </title>
        <style>
            h3 {
                border: solid green;
                border-right-width: initial;
                width: 50%;
            }
            p {
                border-style:dotted;
                border-right-width:initial;
                width:70%;
            }
        </style>
    </head>

    <body>
        <center>
            <h1 style = "color:green">
             GeeksForGeeks
            </h1>
            <h2>border-right-width:initial;</h2>

            <!-- border-right-width property
                                   used here -->
            <h3>GeeksForGeeks</h3>

            <!-- border-right-width property
                                   used here -->

            <p>
             It is a computer science portal for geeks.
            </p>

        </center>
    </body>
</html>
```

*   **输出：**

![](img/780ec1c77a399b7a36ee15e7fc467db9.png)

## 支持的浏览器
`border-right-width` 属性支持的浏览器如下：

*   Google Chrome 1.0
*   Internet Explorer 4.0
*   Firefox 1.0
*   Opera 3.5
*   Apple Safari 1.0