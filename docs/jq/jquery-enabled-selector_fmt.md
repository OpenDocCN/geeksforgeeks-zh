# jQuery :enabled 选择器

> 原文: [https://www.geeksforgeeks.org/jquery-enabled-selector/](https://www.geeksforgeeks.org/jquery-enabled-selector/)

## 概述

**:enabled** 选择器用于选择所有启用的表单元素。

## 语法

```javascript
$(":enabled")
```

## 参数

*   **:enabled** 选择器：用于选择支持禁用属性的 HTML 元素。即 `button` 标签、`input` 标签、`optgroup` 标签、`option` 标签、`select` 标签和 `textarea` 标签。

## 示例-1

```html
<!DOCTYPE html>
<html>
<head>
    <title>:enabled Selector</title>
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js"></script>
    <script>
        $(document).ready(function() {
            $(":enabled").css("background-color", "green");
        });
    </script>
</head>
<body>
    <center>
        <form action="#">
            <h1>Welcome to GeeksforGeeks!.</h1>
            <div>
                Text :
                <input type="text" name="text" value="GeeksforGeeks">
                <br/>
                <input type="submit" name="submit" value="submit">
            </div>
        </form>
    </center>
</body>
</html>
```

**输出:**
![](img/6b9f731de90932ec04f4ef4043b8a4a6.png)

## 示例-2

```html
<!DOCTYPE html>
<html>
<head>
    <title>:enabled Selector</title>
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js"></script>
    <script>
        $(document).ready(function() {
            $(":enabled").css("background-color", "green");
        });
    </script>
</head>
<body>
    <center>
        <form action="#">
            <h1>Welcome to GeeksforGeeks!.</h1>
            <div>
                Select :
                <select>
                    <option>1</option>
                    <option>2</option>
                    <option>3</option>
                    <option>4</option>
                </select>
            </div>
        </form>
    </center>
</body>
</html>
```

**输出**
![](img/b04aec1e52671a32b9238eebd4f9fae6.png)