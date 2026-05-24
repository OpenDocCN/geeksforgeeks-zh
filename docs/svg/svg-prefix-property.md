# SVG 前缀属性

> 原文:[https://www.geeksforgeeks.org/svg-prefix-property/](https://www.geeksforgeeks.org/svg-prefix-property/)

SVG `<em>`前缀属性返回给定属性元素的前缀

**语法:**

```html
string = attribute.prefix

```

**返回值:**该属性返回Attr 的前缀。

**例 1:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<body>
    <svg viewBox="0 0 100 100" 
        xmlns="http://www.w3.org/2000/svg">

        <!-- A link around a text -->
        <text id="example" x="20" y="20">
            Click me
        </text>

        <script>
            const element = document
                .querySelector("#example");

            const attribute = element.attributes[0];
            console.log(attribute.prefix);
        </script>
    </svg>
</body>

</html>
```

**输出:**

![](img/189e4b00a4171352e94b90f3187a5e66.png)
![](img/7bed081f0cdfde8320ec1a50d77140c2.png)

**例 2:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<body>
    <svg viewBox="0 0 100 100" 
        xmlns="http://www.w3.org/2000/svg">

        <!-- A link around a shape -->
        <circle id="example" cx="20" 
            cy="20" r="15">
            Click me
        </circle>

        <script>
            const element = document
                .querySelector("#example");

            const attribute = element.attributes[0];
            console.log(attribute.prefix);
        </script>
    </svg>
</body>

</html>
```

**输出:**

![](img/5d804f93b8dd10d92fee0d52e7e849ce.png)
![](img/7bed081f0cdfde8320ec1a50d77140c2.png)