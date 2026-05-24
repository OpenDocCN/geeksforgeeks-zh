# CSS: 占位符显示选择器

> 原文: [https://www.geeksforgeeks.org/css-placeholder-shown-selector/](https://www.geeksforgeeks.org/css-placeholder-shown-selector/)

CSS `:placeholder-shown` 伪类选择具有占位符文本的 `input` 元素或 `textarea` 元素。`:placeholder-shown` 和 `:placeholder` 的主要区别在于 `:placeholder-shown` 是在显示占位符文本时选择输入本身，而 `:placeholder` 是给占位符文本赋予风格。

## 语法

```css
:placeholder-shown
{
   /* CSS Property */ 
}
```

## 示例 1

以下是说明使用 `:placeholder-shown` 属性的示例。

### 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <style>
        input {
            border: 1px solid black;
            padding: 10px;
        }

        input:placeholder-shown {
            border-color: rgb(255, 114, 58);
            color: rgb(24, 187, 97);
        }
    </style>
</head>

<body>

<h1 style="color: green;">GeeksforGeeks</h1>
    <input placeholder="Computer Science portal !">
</body>

</html>
```

**输出:**

![](img/5e4fed7afbac526561922bb4f990b0cf.png)

## 示例 2

以下是说明使用 `:placeholder-shown` 属性的示例。

### 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <style>
        input.studentid:placeholder-shown {
            background-color: yellow;
            color: red;
        }
    </style>
</head>

<body>
    <h1 style="color: green;">GeeksforGeeks</h1>

    <form>
        <p>
            <label for="branch">Enter Geek Name:</label>
            <input id="branch" placeholder="Geek Branch" />
        </p>

        <p>
            <label>Enter Geek ID:</label>
            <input type="number" pattern="[0-9]{7}" 
            class="studentid" placeholder="7 digit id" />
        </p>
    </form>
</body>

</html>
```

**输出:**

![](img/1e49b45a9bf539ac973eaa90866ef09d.png)

## 支持的浏览器

*   Chrome
*   Firefox
*   Safari
*   Opera
*   Edge
*   Internet Explorer (不支持)。