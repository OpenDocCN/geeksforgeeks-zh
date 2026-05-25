# HTML DOM 文档隐藏属性

> 原文：[https://www.geeksforgeeks.org/html-dom-document-hidden-property/](https://www.geeksforgeeks.org/html-dom-document-hidden-property/)

`document.hidden` 属性返回一个布尔值，指示页面是否被视为隐藏。这是只读属性。

## 语法

```html
var bool = document.hidden;
```

## 返回值

该属性返回一个布尔值：
*   如果页面被认为是隐藏的，则为 `true`。
*   如果页面未被视为隐藏，则为 `false`。

## 示例

这个示例展示了如何使用这个属性来检查页面是否隐藏。

```html
<!DOCTYPE html>
<html>

<body>
    <h1>GeeksforGeeks</h1>

    <button onclick="get()">
        Check
    </button>

    <script type="text/javascript">
        function get() {
            alert(document.hidden);
        }
    </script>
</body>

</html>
```

**输出：**

*   **点击按钮前：**
    ![](img/0d05b6923d3d9914acac51c09f8ba248.png)

*   **点击按钮后：**
    ![](img/6fc2846990d45325390eea6f99e71ab5.png)

## 支持的浏览器

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   歌剧
*   旅行队