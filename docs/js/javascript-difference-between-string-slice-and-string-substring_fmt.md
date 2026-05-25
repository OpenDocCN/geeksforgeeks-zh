# JavaScript中`String.slice()`与`String.substring()`的区别

> 原文：[https://www.geeksforgeeks.org/javascript-difference-between-string-slice-and-string-substring/](https://www.geeksforgeeks.org/javascript-difference-between-string-slice-and-string-substring/)

这两个函数的语法非常相似，但在某些情况下有所不同。让我们看看它们之间的区别。

## 1. `slice()`
此方法*选择字符串的一部分，并将选中的部分作为新字符串返回*。使用起始和结束参数来指定要提取的部分。
第一个字符的索引为0。

**语法：**
```javascript
str.slice(start, end)
```

**参数：**
*   `start`：此参数为必填项。它指定开始提取的位置。第一个字符从位置0开始。
*   `end`：此参数为可选。停止选择的位置（最多，但不包括）。如果省略参数，函数将选择从起始参数到字符串结尾的所有字符。

## 2. `substring()`
此函数的语法与`slice()`相同。
此*方法选择字符串的一部分，并将选中的部分作为新字符串返回*。使用起始和结束参数来指定要提取的部分。
第一个字符的索引为0。

**语法：**
```javascript
str.substring(start, end)
```

**参数：**
*   `start`：此参数为必填项。它指定开始提取的位置。第一个字符从位置0开始。
*   `end`：此参数为可选。停止选择的位置（最多，但不包括）。如果省略参数，函数将选择从起始参数到字符串结尾的所有字符。

## 共同结果
两者在给定的情况下给出相同的结果。
1.  如果`start == stop`，两者都返回一个空字符串。
2.  如果省略`stop`，两者都将提取字符直到字符串结束。
3.  如果任何参数大于字符串的长度，则在这种情况下将使用字符串的长度。

## `substring()`的特殊行为
1.  如果`start > stop`，则函数交换两个参数。
2.  如果任何参数为负或为`NaN`，则视为0。

## `slice()`的特殊行为
1.  如果`start > stop`，该函数将返回一个空字符串（`""`）。
2.  如果`start`为负，它从字符串的末尾开始设置字符，如`substr()`。
3.  如果`stop`为负，则设置`stop = string.length – Math.abs(stop)`（初始值）。

这里有几个例子。

### 示例-1
这两个示例在两种情况下给出了相同的结果。

```html
<!DOCTYPE html>
<html>
<head>
    <title>
        JavaScript | difference between String.slice and String.substring
    </title>
</head>
<body style="text-align:center;">
    <h1 style="color:green;">GeeksForGeeks</h1>
    <p id="GFG_UP"></p>
    <button onclick="Geeks()">Click Here</button>
    <p id="GFG_DOWN" style="color:green;"></p>
    <script>
        var str = "This is GeeksForGeeks";
        var up = document.getElementById("GFG_UP");
        var down = document.getElementById("GFG_DOWN");
        up.innerHTML = "Str = '" + str + "'";

        function Geeks() {
            down.innerHTML = "str.slice() = " + str.slice(0, 13) +
                "<br>str.substring() = " + str.substring(0, 13);
        }
    </script>
</body>
</html>
```

**输出：**
*   **点击按钮前：**
    ![](img/12d1e0e80e353310dd712527aac59dd3.png)
*   **点击按钮后：**
    ![](img/8014a9a9846c3e154d93c5f5e2eae346.png)

### 示例-2
在本例中，如果是`substring()`，当`start > stop`时，它交换参数，而`slice()`返回空字符串。

```html
<!DOCTYPE html>
<html>
<head>
    <title>
        JavaScript | difference between String.slice and String.substring
    </title>
</head>
<body style="text-align:center;">
    <h1 style="color:green;">GeeksForGeeks</h1>
    <p id="GFG_UP"></p>
    <button onclick="Geeks()">Click Here</button>
    <p id="GFG_DOWN" style="color:green;"></p>
    <script>
        var str = "This is GeeksForGeeks";
        var up = document.getElementById("GFG_UP");
        var down = document.getElementById("GFG_DOWN");
        up.innerHTML = "Str = '" + str + "'";

        function Geeks() {
            down.innerHTML = "str.slice() = " + str.slice(13, 0) +
                "<br>str.substring() = " + str.substring(13, 0);
        }
    </script>
</body>
</html>
```

**输出：**
*   **点击按钮前：**
    ![](img/12d1e0e80e353310dd712527aac59dd3.png)
*   **点击按钮后：**
    ![](img/906aef95d4ab73cca98be801c2db4810.png)

### 示例-3
在本例中，在`substring()`的情况下，负参数被视为0，而`slice()`返回空字符串。

```html
<!DOCTYPE html>
<html>
<head>
    <title>
        JavaScript | difference between String.slice and String.substring
    </title>
</head>
<body style="text-align:center;">
    <h1 style="color:green;">GeeksForGeeks</h1>
    <p id="GFG_UP"></p>
    <button onclick="Geeks()">Click Here</button>
    <p id="GFG_DOWN" style="color:green;"></p>
    <script>
        var str = "This is GeeksForGeeks";
        var up = document.getElementById("GFG_UP");
        var down = document.getElementById("GFG_DOWN");
        up.innerHTML = "Str = '" + str + "'";

        function Geeks() {
            down.innerHTML = "str.slice() = " + str.slice(-13, 7) +
                "<br>str.substring() = " + str.substring(-13, 7);
        }
    </script>
</body>
</html>
```

**输出：**
*   **点击按钮前：**
    ![](img/12d1e0e80e353310dd712527aac59dd3.png)
*   **点击按钮后：**
    ![](img/edf5bdc51c8b737433f414f7f01838eb.png)