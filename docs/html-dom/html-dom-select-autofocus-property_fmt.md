# HTML DOM Select autofocus 属性

> 原文：[https://www.geeksforgeeks.org/html-dom-select-autofocus-property/](https://www.geeksforgeeks.org/html-dom-select-autofocus-property/)

HTML DOM 中的 `select` `autofocus` 属性用于**设置**或**返回**下拉列表在页面加载时是否自动获得焦点。
如果下拉列表自动获得焦点，属性返回 `true`，否则返回 `false`。
`select` `autofocus` 属性反映 HTML `autofocus` 属性。

## 返回 autofocus 属性的语法

```html
selectObject.autofocus
```

## 设置 autofocus 属性的语法

```html
selectObject.autofocus = true|false
```

## 属性值

*   `true`: 下拉列表获得自动对焦。
*   `false`: 有默认值。下拉列表没有焦点。

## 返回值

返回一个布尔值，表示下拉列表是否有焦点。

下面的程序说明了 `select` `autofocus` 属性：

### 示例 1

找出下拉列表是否在页面加载时自动获得焦点。

```html
<!DOCTYPE html>
<html>

<head>
    <title>
      Select Autofocus Property in HTML
  </title>
    <style>
        h1 {
            color: green;
        }

        h2 {
            font-family: Impact;
        }

        body {
            text-align: center;
        }
    </style>
</head>

<body>

<h1>
      GeeksforGeeks
  </h1>
    <h2>
      Select Autofocus Property
  </h2>
    <br>
  Select your preferred course from the drop-down list:

<select id="Courses" autofocus>
        <option value="C++">c++</option>
        <option value="Placement">Placement</option>
        <option value="Java">Java</option>
        <option value="Python">Python</option>
    </select>

<p>
      To find out if the drop-down list
      automatically gets focused upon page load
      or not, double-click the "Check" button.
  </p>

<button onclick="My_list()">Check</button>

<p id="test"></p>

<script>
        function My_list() {
            var d =
                document.getElementById("Courses").autofocus;
            document.getElementById("test").innerHTML = d;
        }
    </script>

</body>

</html>
```

**输出：**

**点击按钮前：**

![](img/d04e53a740d6ff0c5c7ecbe53f264085.png)

**点击按钮后：**

![](img/c15aa81bd935e260e9cf16bc943925e3.png)

## 支持的浏览器

`DOM` `Select` `autofocus` 属性支持的浏览器如下：

*   谷歌 Chrome
*   Internet Explorer 10.0 +
*   火狐浏览器
*   歌剧
*   旅行队