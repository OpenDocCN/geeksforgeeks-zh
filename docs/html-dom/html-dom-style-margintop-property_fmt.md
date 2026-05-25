# HTML DOM 样式边距属性

> 原文: [https://www.geeksforgeeks.org/html-dom-style-margintop-property/](https://www.geeksforgeeks.org/html-dom-style-margintop-property/)

HTML DOM 中的样式边距属性用于设置或返回元素的上边距。

## 语法

它返回 `marginTop` 属性。

```html
object.style.marginTop
```

它用于设置 `marginTop` 属性。

```html
object.style.marginTop = "length|percentage|auto|initial|inherit"
```

## 返回值

它返回一个代表元素上边距的字符串值。

## 属性值

**length:** 用于以固定单位指定边距。其默认值是 `0`。

### 示例

```html
<!DOCTYPE html>
<html>
<head>
    <title>DOM Style marginTop Property</title>
</head>
<body>
    <h1 style="color: green">GeeksforGeeks</h1>
    <b>DOM Style marginTop Property</b>
    <div class="container">
        <div class="div1">Line One</div>
        <div class="div2">Line Two</div>
        <button onclick="setMargin()">Change marginTop</button>
    </div>
    <!-- Script to set top margin -->
    <script>
        function setMargin() {
            elem = document.querySelector('.div1');
            elem.style.marginTop = '50px';
        }
    </script>
</body>
</html>
```

### 输出

点击按钮前:
![length-before](img/cea62d89a3a3262237c9a9938d7cf6a7.png)

点击按钮后:
![length-after](img/19933c9b9258b610dd30752adc45c45e.png)

**percentage:** 用于将边距量指定为相对于包含元素宽度的百分比。

### 示例

```html
<!DOCTYPE html>
<html>
<head>
    <title>DOM Style marginTop Property</title>
</head>
<body>
    <h1 style="color: green">GeeksforGeeks</h1>
    <b>DOM Style marginTop Property</b>
    <div class="container">
        <div class="div1">Line One</div>
        <div class="div2">Line Two</div>
        <button onclick="setMargin()">Change marginTop</button>
    </div>
    <!-- Script to set top margin -->
    <script>
        function setMargin() {
            elem = document.querySelector('.div1');
            elem.style.marginTop = '20%';
        }
    </script>
</body>
</html>
```

### 输出

点击按钮前:
![percentage-before](img/eca729a1dec4747a797b38b9cd55f635.png)

点击按钮后:
![percentage-after](img/658d2bc91d3727df7501a05b72859e7a.png)

**auto:** 如果值设置为 `auto`，则浏览器会自动计算合适的边距大小。

### 示例

```html
<!DOCTYPE html>
<html>
<head>
    <title>DOM Style marginTop Property</title>
</head>
<body>
    <h1 style="color: green">GeeksforGeeks</h1>
    <b>DOM Style marginTop Property</b>
    <div class="container">
        <div class="div1" style="margin-top: 50px;">Line One</div>
        <div class="div2">Line Two</div>
        <button onclick="setMargin()">Change marginTop</button>
    </div>
    <!-- Script to set top margin -->
    <script>
        function setMargin() {
            elem = document.querySelector('.div1');
            elem.style.marginTop = 'auto';
        }
    </script>
</body>
</html>
```

### 输出

点击按钮前:
![auto-before](img/6da744b44942d33a71fe8d69a16c77fe.png)

点击按钮后:
![auto-after](img/63ffea32212c3a20220e07f70e01193d.png)

**initial:** 用于将属性设置为其默认值。

### 示例

```html
<!DOCTYPE html>
<html>
<head>
    <title>DOM Style marginTop Property</title>
</head>
<body>
    <h1 style="color: green">GeeksforGeeks</h1>
    <b>DOM Style marginTop Property</b>
    <div class="container">
        <div class="div1" style="margin-top: 50px;">Line One</div>
        <div class="div2">Line Two</div>
        <button onclick="setMargin()">Change marginTop</button>
    </div>
    <!-- Script to set top margin -->
    <script>
        function setMargin() {
            elem = document.querySelector('.div1');
            elem.style.marginTop = 'initial';
        }
    </script>
</body>
</html>
```

### 输出

点击按钮前:
![initial-before](img/0a4bc304c2cba1786c92a53bb2638c8e.png)

点击按钮后:
![initial-after](img/1c072a6fc3b15c83b114110b16df802f.png)

**inherit:** 用于从其父元素继承值。

### 示例

```html
<!DOCTYPE html>
<html>
<head>
    <title>DOM Style marginTop Property</title>
</head>
<body>
    <h1 style="color: green">GeeksforGeeks</h1>
    <b>DOM Style marginTop Property</b>
    <div class="container">
        <div class="div1" style="margin-top: 50px;">Line One</div>
        <div class="div2">Line Two</div>
        <button onclick="setMargin()">Change marginTop</button>
    </div>
    <!-- Script to set top margin -->
    <script>
        function setMargin() {
            elem = document.querySelector('.div1');
            elem.style.marginTop = 'inherit';
        }
    </script>
</body>
</html>
```

### 输出

点击按钮前:
![inherit-before](img/1217db223fccb880892d3ecd299e4f3a.png)

点击按钮后:
![inherit-after](img/51bee90bf8c19ea399f2af63653979a3.png)

## 支持的浏览器

`DOM Style marginTop` 属性支持的浏览器如下:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   歌剧
*   旅行队