# jQuery 中如何按属性选择元素？

> 原文: [https://www.geeksforgeeks.org/how-to-select-elements-by-attribute-in-jquery/](https://www.geeksforgeeks.org/how-to-select-elements-by-attribute-in-jquery/)

jQuery 是一个轻量级的 JavaScript 库。在普通的 JavaScript 语言中，`getElementById` 方法用于选择一个元素。然而，出于同样的目的，jQuery 提供了一个轻得多的替代方案。“jQuery 选择器”允许用户操作 HTML 元素和其中的数据（DOM 操作）。

## 语法

```html
$("[attribute=value]")
```

这里，`attribute` 和 `value` 是必需的。

## 一些最常用的 jQuery 选择器

| 句法 | 例子 | 选择 |
| --- | --- | --- |
| `*` | `$("*")` | 网页上的所有元素 |
| `#id` | `$("#geek")` | id 为“geek”的元素 |
| `.class` | `$(".geek")` | class=“geek”的所有元素 |
| `:first` | `$("p:first")` | 网页的第一个“p”元素 |
| `:header` | `$(":header")` | 所有标题元素，如 h1、h2、h3、h4 等 |
| `:empty` | `$(":empty")` | 所有的空元素 |
| `:input` | `$(":input")` | 所有输入元素，如文本、密码等 |
| `:text` | `$(":text")` | `type="text"` 的输入元素 |
| `:last-child` | `$("p:last-child")` | 那些“p”元素是它们父母的最后一个孩子 |
| `:animated` | `$(":animated")` | 网页上的所有动画元素 |

## #id 选择器

id 选择器为要选择的元素指定一个 id。它不应该以数字开头，并且 `id` 属性在文档中必须是唯一的，这意味着它只能使用一次。

### 语法

```html
$("#example")
```

`id` 选择器必须仅在用户想要查找唯一元素时使用。

### 示例

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        How to select elements from
        attribute in jQuery ?
    </title>

<script src=
"https://ajax.googleapis.com/ajax/libs/jquery/3.4.1/jquery.min.js">
    </script>

<script>
        $(document).ready(function() {
            $("button").click(function() {
                $("#para").hide();
            });
        });
    </script>
</head>

<body>
    <h2>GeeksforGeeks</h2>

<p>This is a constant paragraph.</p>

<p id="para">
        This paragraph will get hidden once
        the button is clicked.
    </p>

<button>Click me</button>
</body>

</html>
```

### 输出

*   **之前点击按钮:**
    ![](img/482ce654abd09c2febce3c64d59a264c.png)
*   **点击按钮后:**
    ![](img/bce08149b0f05eeab8fb30ceb00478c1.png)

## .class 选择器

类选择器指定要选择的元素的类。它不应该以数字开头。它为几个 HTML 元素赋予了样式。

### 语法

```html
$(".example")
```

### 示例

```html
<!DOCTYPE html>
<html>

<head>
    <script src=
"https://ajax.googleapis.com/ajax/libs/jquery/3.4.1/jquery.min.js">
    </script>

<script>
        $(document).ready(function() {
            $("button").click(function() {
                $(".test").hide();
            });
        });
    </script>
</head>

<body>
    <h2 class="heading">GeeksForGeeks</h2>

<p class="test">This is a paragraph.</p>
    <p class="test">This is another paragraph.</p>

<button>Click me</button>
</body>

</html>
```

### 输出

*   **之前点击按钮:**
    ![](img/4c801e10c695d2c3475b1a85dc25c58d.png)
*   **点击按钮后:**
    ![](img/a2e405de3a684b402e6e05e6b0e03df6.png)

## :first 选择器

是一个 jQuery 选择器，用于选择指定类型的第一个元素。

### 语法

```html
$(":first")
```

### 示例

```html
<!DOCTYPE html>
<html>

<head>
    <title>jQuery :first selector</title>

<script src=
"https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js">
    </script>

<script>
        $(document).ready(function() {
            $("p:first").css(
            "background-color", "green");
        });
    </script>
</head>

<body>
    <h1>GeeksforGeeks</h1>
    <p>jQuery</p>
    <p>JavaScript</p>
    <p>PHP</p>
</body>

</html>
```

### 输出
![](img/e03676d49ad3ed050dd58a6063ed31d6.png)