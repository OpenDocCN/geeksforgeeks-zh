# HTML DOM meta name 属性

> 原文：[https://www.geeksforgeeks.org/html-dom-meta-name-property/](https://www.geeksforgeeks.org/html-dom-meta-name-property/)

**HTML DOM meta name 属性**用于返回或设置 `<meta>` 元素的 `name` 属性值。当用户提交表单数据时，该属性用于引用表单数据。它也用于在 JavaScript 中引用该元素。

## 语法

*   它用于返回 `name` 属性。

```html
metaObject.name
```

*   它用于设置 `name` 属性。

```html
metaObject.name = name
```

## 属性值

*   **name:** 指定 `<meta>` 元素的名称。

## 返回值

返回一个代表 `<meta>` 元素名称的字符串值。

## 示例

### 示例 1

这个程序说明了如何返回 `name` 属性。

```html
<!DOCTYPE html> 
<html>

<head> 
    <meta name="keywords"
        content="Meta Tags, Metadata"  /> 
</head>

<body> 
    <center> 
        <h1>GeeksForGeeks</h1> 
        <h2>DOM Meta name Property</h2> 
        <p>Hello GeeksforGeeks!</p>

<button onclick="myGeeks()"> 
        Submit</button>

<p id="sudo"></p>

<script> 
            function myGeeks() { 
                var x = 
                document.getElementsByTagName( 
                "META")[0].name;
                ;

document.getElementById( 
                "sudo").innerHTML = x; 
            } 
        </script> 
</center> 
</body>

</html>
```

**输出:**

**点击按钮前:**
![](img/c7207fc0c5e4f21a7d1550f7aaa9daee.png)

**点击按钮后:**
![](img/62bc777684ac5416519efe5364be59bf.png)

### 示例 2

该程序说明了如何设置 `name` 属性。

```html
<!DOCTYPE html> 
<html>

<head> 
    <meta name="keywords"
        content="Meta Tags, Metadata"  /> 
</head>

<body> 
    <center> 
        <h1>GeeksForGeeks</h1> 
        <h2>DOM Meta name Property</h2> 
        <p>Hello GeeksforGeeks!</p>

<button onclick="myGeeks()"> 
        Submit</button>

<p id="sudo"></p>

<script> 
            function myGeeks() { 
                var x = 
                document.getElementsByTagName( 
                "META")[0].name = "Hello Geeks";
                ;

document.getElementById( 
                "sudo").innerHTML = x; 
            } 
        </script> 
</center> 
</body>

</html>
```

**输出:**

**点击按钮前:**
![](img/c7207fc0c5e4f21a7d1550f7aaa9daee.png)

**点击按钮后:**
![](img/59c6f61b5150fedfb31f865308e7b55d.png)

## 支持的浏览器

**DOM meta name 属性**支持的浏览器如下:

*   谷歌 Chrome
*   微软 Internet Explorer
*   火狐浏览器
*   苹果 Safari
*   Opera