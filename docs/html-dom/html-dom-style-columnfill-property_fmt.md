# HTML | DOM 样式列填充属性

> 原文: [https://www.geeksforgeeks.org/html-dom-style-columnfill-property/](https://www.geeksforgeeks.org/html-dom-style-columnfill-property/)

## 属性介绍

HTML DOM Style `columnFill` 属性指定如何填充一列（平衡或不平衡）。

## 语法

### 获取属性

```html
object.style.columnFill
```

### 设置属性

```html
object.style.columnFill = "balance|initial|auto|inherit"
```

## 属性值

*   `balance`: 平衡列（默认）。
*   `auto`: 列将有不同的长度并依次填充。
*   `initial`: 设置默认值。
*   `inherit`: 从父元素继承值。

## 示例

```html
<!DOCTYPE html>
<html>
<head>
    <title>
        HTML | DOM Style columnFill Property
    </title>
</head>
<body>
    <div id="example">
        GEEKSFORGEEKS welcomes you to the learning portal.
        GEEKSFORGEEKS welcomes you to the learning portal.
        GEEKSFORGEEKS welcomes you to the learning portal.
        GEEKSFORGEEKS welcomes you to the learning portal.
        GEEKSFORGEEKS welcomes you to the learning portal.
        GEEKSFORGEEKS welcomes you to the learning portal.
        GEEKSFORGEEKS welcomes you to the learning portal.
        GEEKSFORGEEKS welcomes you to the learning portal.
        GEEKSFORGEEKS welcomes you to the learning portal.
        GEEKSFORGEEKS welcomes you to the learning portal.
        GEEKSFORGEEKS welcomes you to the learning portal.
        GEEKSFORGEEKS welcomes you to the learning portal.
        GEEKSFORGEEKS welcomes you to the learning portal.
        GEEKSFORGEEKS welcomes you to the learning portal.
        GEEKSFORGEEKS welcomes you to the learning portal.
        GEEKSFORGEEKS welcomes you to the learning portal.
    </div>
    <button onclick="split()">click</button>
    <script>
        function split() {
            document.getElementById("example").style.columnFill = "auto";
        }
    </script>
</body>
</html>
```

## 备注与浏览器支持

**注:** CSS3 `column-fill` 属性在 Firefox 13.0+ 中受 `-moz-` 前缀支持。

**支持的浏览器:** 主要浏览器不支持 HTML DOM Style `columnFill` 属性。